from datetime import datetime

f = open('http_access_log', 'r')

lineList = []
byWeekday = {0:0, 1:0, 2:0, 3:0, 4:0, 5:0, 6:0}

count = 0
for line in f:
	count += 1
	lineList.append(line)

for i in range(len(lineList)):
	splitLine = lineList[int(i)].split()

	try: date = splitLine[3][1:12]

	except: pass

	#print(date)
	try: formatted_date = datetime.strptime(date, "%d/%b/%Y")
	except: pass

	byWeekday[formatted_date.weekday()] += 1

#print(byWeekday[0])
weekDays = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday']
for i in range(7):
	print('Requests made on '+ weekDays[i]+ ': '+ str(byWeekday[i]))
#print(len(lineList))
