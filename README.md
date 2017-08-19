# midterm-homework
Crossinclass 9-3
report_all = []
with open ('report.txt','r',encoding = 'utf-8') as f: 
    report_all = f.readlines()
courses = len(report_all[0].split()) - 1    #切片第一个同学的科目数
sum_c = [0 for i in range(courses)]    #新增重置科目列表
for line in report_all:
    data = line.split()
    sum_s = 0
    for score in data[1:]:
        sum_s += int(score)     #每个同学总分
        average_s = round(float(sum_s)/(len(data) - 1), 1)     #每个同学平均分
    result = '%s' % (data[0]) + ' '.join(data[1:]) + ' %d %d' % (sum_s, average_s)
    result_s.append(result)
    result_s.sort(key = lambda s : s[10], reverse = True)
print(result_s)
for goal in range(1, len(data)):
    sum_c[goal-1] += int(data[goal])    #每个科目总分
average_c = [round(float(i) / len(report_all), 1) for i in sum_c]    #每个科目平均分
result = '%d  %s' % (goal, data[0]) + ' '.join(data[1:]) + ' %d  %d' % (sum_s, average_s)
result_s.append(result)
print(result_s)
