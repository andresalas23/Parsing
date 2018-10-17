def most_least():	#clear
	import operator
	
	f = open('local_copy.txt', 'r')
	
	list_for_line = []
	reqCount = {}
	file_list = []
	
	count = 0
	for line in f:
		count+=1
		list_for_line.append(line)
	
	for i in range(len(list_for_line)):
		listSplit = list_for_line[int(i)].split()
		try: reqFile = listSplit[6]
		except: pass
		file_list.append(reqFile)
	
	for key in file_list:
		if key not in reqCount:
			reqCount[key] = 1
		else:
			if key in reqCount:
				reqCount[key] += 1
	
	
	
	mostRequested = max(reqCount.items(), key=operator.itemgetter(1))[0]
	leastRequested = min(reqCount.items(), key=operator.itemgetter(1))[0]
	
	print(str(mostRequested) + ' was requested the most, at ' + str(reqCount['index.html']) + ' times')
	print(str(leastRequested) + ' was requested the least, at ' + str(reqCount['7512.map?159,276']) + ' times')
	
   
	
def redirect():			#clear
	import re
	
	f = open('local_copy.txt', 'r')
	
	list_for_line = []
	list_for_status = []
	
	count = 0
	for line in f:
		count += 1
		list_for_line.append(line)
	
	for i in range(len(list_for_line)):
		splitLine = list_for_line[int(i)].split()
	
		try: status = splitLine[8]
		except: pass
	
		try: statusint = int(status)
		except: pass
	
		list_for_status.append(statusint)
	
	number_of_successful=0
	for i in list_for_status:
		if 300 <= i <= 399:
			number_of_successful += 1
	
	ans=round(100*(number_of_successful/726736.0))
	
	print("Rounded percentage of redirected requests: %s%%" % ans ) 
	
def unsuccessful():		#clear
	import re
	
	f = open('local_copy.txt', 'r')
	
	list_for_line = []
	list_for_status = []
	
	count = 0
	for line in f:
		count += 1
		list_for_line.append(line)
	
	for i in range(len(list_for_line)):
		splitLine = list_for_line[int(i)].split()
	
		try: status = splitLine[8]
		except: pass
	
		try: statusint = int(status)
		except: pass
	
		list_for_status.append(statusint)
	
	number_of_unsuccessful=0
	for i in list_for_status:
		if 400 <= i <= 499:
			number_of_unsuccessful += 1
			
	ans=round(100*(number_of_unsuccessful/726736.0))
	              
	print("Rounded percentage of unsuccessful requests : %s%%" % ans ) 
	
def by_month():				#clear
	from datetime import datetime
	import re
	
	f = open('local_copy.txt', 'r')
	
	list_for_line = []
	months_of_1994 = {1:0, 2:0, 3:0, 4:0, 5:0, 6:0, 7:0, 8:0, 9:0, 10:0, 11:0, 12:0}
	months_of_1995 = {1:0, 2:0, 3:0, 4:0, 5:0, 6:0, 7:0, 8:0, 9:0, 10:0, 11:0, 12:0}
	
	outfile1 =open('January.txt', 'w')
	outfile2 =open('Febuary.txt', 'w')
	outfile3 =open('March.txt', 'w')
	outfile4 =open('April.txt', 'w')
	outfile5 =open('May.txt', 'w')
	outfile6 =open('June.txt', 'w')
	outfile7 =open('July.txt', 'w')
	outfile8 =open('August.txt', 'w')
	outfile9 =open('September.txt', 'w')
	outfile10 =open('October.txt', 'w')
	outfile11 =open('November.txt', 'w')
	outfile12 =open('December.txt', 'w')
	
	count = 0
	for line in f:
		count += 1
		list_for_line.append(line)
	
	for i in range(len(list_for_line)):
		splitLine = list_for_line[int(i)].split()
	
		try: date = splitLine[3][1:12]
	
		except: pass
	
		
		try: formatted_date = datetime.strptime(date, "%d/%b/%Y")
		except: pass
	
		for key in months_of_1994:
			if formatted_date.isocalendar()[0] == 1994:
				if formatted_date.month == key:
					months_of_1994[formatted_date.month] += 1
			else: 
				if formatted_date.month == key:
					months_of_1995[formatted_date.month] += 1
	
	months = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'June', 'July', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec']
	for i in range(12):
		print('1994: Requests made on '+ months[i]+ ': '+ str(months_of_1994[i+1]))
		
		
	
	for i in range(12):
		print('1995: Requests made on '+ months[i]+ ': '+ str(months_of_1995[i+1]))
		
	outfile1.close()
	outfile2.close()
	outfile3.close()
	outfile4.close()
	outfile5.close()
	outfile6.close()
	outfile7.close()
	outfile8.close()
	outfile9.close()
	outfile10.close()
	outfile11.close()
	outfile12.close()
	
	

def by_week():				#clear
	from datetime import datetime
	
	f = open('local_copy.txt', 'r')
	
	list_for_line = []
	weeks_in_1994 = {}
	weeks_in_1995 = {}
	count = 0
	for line in f:
		count += 1
		list_for_line.append(line)
	
	for i in range(len(list_for_line)):
		splitLine = list_for_line[int(i)].split()
	
		try: date = splitLine[3][1:12]
	
		except: pass
	
		#print(date)
		try: formatted_date = datetime.strptime(date, "%d/%b/%Y")
		except: pass
	
		#byWeek[formatted_date.weekday()] += 1
		iso_tuple = formatted_date.isocalendar()
		#print(iso_tuple[0])
		for key in range(53):
			if 1994 == iso_tuple[0]:
				if key not in weeks_in_1994.keys():
					weeks_in_1994[key] = 0
				else:
					if key == iso_tuple[1]:
						weeks_in_1994[key] += 1
			if 1995 == iso_tuple[0]:
				if key not in weeks_in_1995.keys():
					weeks_in_1995[key] = 0
				else:
					if key == iso_tuple[1]:
						weeks_in_1995[key] += 1
	
	
	#print(weeks_in_1994)
	#print(weeks_in_1995)
	
	week = []
	strings='week'
	for i in range(53):
		week_number = strings + ' ' + str(i)
		week.append(week_number)
	
	for key in range(53):
			print('1994: Requests made on '+ week[key]+ ': '+ str(weeks_in_1994[key]))
	for key in range(53):
			print('1995: Requests made on '+ week[key]+ ': '+ str(weeks_in_1995[key]))

def by_day():				#clear
	from datetime import datetime
	
	f = open('local_copy.txt', 'r')
	
	list_for_line = []
	day_of_week = {0:0, 1:0, 2:0, 3:0, 4:0, 5:0, 6:0}
	
	count = 0
	for line in f:
		count += 1
		list_for_line.append(line)
	
	for i in range(len(list_for_line)):
		splitLine = list_for_line[int(i)].split()
	
		try: date = splitLine[3][1:12]
	
		except: pass
	
		#print(date)
		try: formatted_date = datetime.strptime(date, "%d/%b/%Y")
		except: pass
	
		day_of_week[formatted_date.weekday()] += 1
	
	#print(day_of_week[0])
	weekDazz = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday']
	for i in range(7):
		print('Requests made on '+ weekDazz[i]+ ': '+ str(day_of_week[i]))
	#print(len(list_for_line))	
	
def total_count():					#clear
	file = open("local_copy.txt", "r")
	#print file.read()
	count = 0
	for line in file:
		count+=1
	print ("Total number of requests made: ",  count)	
	
def main():
	from urllib.request import urlretrieve
	
	URL_PATH = 'https://s3.amazonaws.com/tcmg476/http_access_log'
	LOCAL_FILE = 'local_copy.txt'
	local_file, headers = urlretrieve(URL_PATH, LOCAL_FILE, lambda x,y,z: print('.', end='', flush=True))
	print()
	total_count()
	print()
	print("Number of requests on each day:")
	by_day()
	print()
	print("Number of requests in each week:")
	by_week()
	print()
	print("Number of requests in each month:")
	by_month()
	print()
	print()
	unsuccessful()
	print()
	print()
	redirect()
	print()
	print("The most and least requested files:")
	most_least()
	
	



main()
		
	
