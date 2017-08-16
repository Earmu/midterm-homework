# midterm-homework
Crossinclass 9-3
        for goal in range(1,  len(data)):
            sum_c[goal-1] += int(data[goal])   #计算每科总分
            average_c = [round(float(i) / len(report_all), 1)  for i in sum_c]    #各科平均分
        average_c.insert(0, '平均')
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
