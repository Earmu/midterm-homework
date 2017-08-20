# midterm-homework
Crossinclass 9-3
report_all = []
result_s = []
result_new = []
result_score = []
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
loop = 1
for l in result_s:
    l.insert(1, loop)
    loop += 1
    result_new.append(l)
for raw in result_new:
    for k in raw[2:11]:
        if int(k) < 60:
            raw[raw.index(k)] = '不及格'
    result_score.append(raw)    #替换不及格
for goal in range(1, len(data)):
    sum_c[goal-1] += int(data[goal])    #每个科目总分
average_c = [round(float(i) / len(report_all), 1) for i in sum_c]#每个科目平均分

with open('report_new.txt', 'w') as fn:
    fn.write('姓名 名次 语文 数学 英语 物理 化学 生物 政治 历史 地理 总分 平均分\n')
    fn.write('0 平均', average_c, '\n')
    for t in result_new:
        fn.write(t, '\n')
