# midterm-homework
Crossinclass 9-3
report_all = []
resultsNew_list = []
with open ('report.txt','r',encoding = 'utf-8') as f: 
    report_all = f.readlines()
    for line in report_all:
        #print (line)
        data = line.split()
        sum_student = 0
        sum_goal = 0
        results = []
        for score in data[1:]:
            sum_student += int(score)
            average = str(round(float(sum_student)/(len(data) - 1), 1))
        class student:
            def __init__(self):
                self.name = data[0]
                self.goal = ' '.join(data[1:])
                self.sumStudent = sum_student
                self.average = average
            def __repr__(self):
                return repr((self.name, self.goal, self.sumStudent, self.average))
        resultsNew = student()
        resultsNew_list.append(resultsNew)
        resultsNew_list.sort(key = average)
    print (resultsNew_list)
#with open('report_new.txt', 'w', encoding = 'utf-8') as output:
    #output.writelines(resultsNew)
