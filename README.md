# calculate-magic-square
def magic_square(my_matrix):
  size=len(my_matrix[0])
  sum_list=[]
  #horizantal 
  sum_list.extend([sum(lines) for lines in my_matrix])
  #vertical
  for column in range(size):
    sum_list.appened(sum(row[column] for row in my_matrix))
  #diagonals
  res1=0
  for i in range(0,size):
    res1+=my_matrix[i][i]
  sum_list.append(res1)
  res2=0
  for i in range(size-1,-1,-1):
    res2+=my_matrix[i][i]
  sum_list.append(res2)
  if len(set(sum_list))>1:
        return False
        return True
m=[[7, 12, 1, 14], [2, 13, 8, 11], [16, 3, 10, 5], [9, 6, 15, 4]] 
print(magic_square(m));
m=[[2, 7, 6], [9, 5, 1], [4, 3, 8]]
print(magic_square(m));
m=[[2, 7, 6], [9, 5, 1], [4, 3, 7]]
print(magic_square(m));
