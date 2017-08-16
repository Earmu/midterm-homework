# midterm-homework
Crossinclass 9-3
report_all = []
resultsNew_list = []
with open ('report.txt', 'r', encoding = 'utf-8') as f: 
    report_all = f.readlines()
    courses = len(report_all[0].split()) - 1    #切片第一个同学的科目数
    sum_c = [0 for i in range(courses)]    #新增重置科目列表
    for line in report_all:
        #print (line)
        data = line.split()
        sum_s = 0
        for score in data[1:]:
            sum_s += int(score)     #每个同学总分
            average_s = round(float(sum_s)/(len(data) - 1), 1)     #每个同学平均分
        #print (sum_s)
        #print (average_s)
        for goal in range(1, len(data)):
            sum_c[goal-1] += int(data[goal])    #每个科目总分
            average_c = [round(float(i) / len(report_all), 1) for i in sum_c]    #每个科目平均分
        average_c.insert(0, '平均')
    #print (sum_c)
    #print (average_c)
        class student:
            def __init__(self):
                self.name = data[0]
                self.goal = ' '.join(data[1:])
                self.sumStudent = sum_s
                self.average = average_s
            def __repr__(self):
                return repr((self.name, self.goal, self.sumStudent, self.average))
        resultsNew = student()
        resultsNew_list.append(resultsNew)
        results_sorted = sorted(resultsNew_list, key=lambda student: student.average, reverse=True)
    results_sorted.insert(0, average_c)
    print (results_sorted)
