#Each biweekly Scenario
import random 
tuesdays = [2,9]
d= {}
#On first day of August
for player_id in range(1,626):
      #what game_id is the player choosing
    game_id = random.randint(0,4)
    d[player_id] = [0,0,0,0,0]
    d[player_id][game_id] += random.randint(75,200)
#print(d)
for day_num in [3,4,5,6,7,8]:
    for player_id in range(1,625):
      game_id = random.randint(0,4)
      d[player_id][game_id] += random.randint(75,200)
print(d)
top5=[]
top55=[]
for temp in range(5):
  for i in range(1,626):
    k = d[i][temp]
    top5.append(k)
  top55=top5[:]
  top55.sort(reverse=True)
  bottom5=top5[:]
  bottom5.sort()
#print(*top5)
#print(*top55)
#print(*bottom5)
  for i in range(5):
    ele = top55[i]
    print("players Id with "+ str(top5.index(ele))+" has stood in "+str(i+1)+" place in game_id="+str(temp+1)+" with a score of "+str(ele))
  print(" ")
  #for knowing bottom5
  for i in range(5):
    ele = bottom5[i]
    print("players Id with "+ str(top5.index(ele))+" has stood in "+str(i+1)+" place from bottom in game_id="+str(temp+1)+" with a score of "+str(ele))
  print(" ")
k1=[]
#Overall Toppers (eventually top5 when taken average as well)
for a in range(1,626):
  k = 0
  for i in range(5):
    k +=d[a][i]
  k1.append(k)
k2=k1[:]
k2.sort(reverse=True)
for i in range(5):
    ele = k2[i]
    print("players Id with "+ str(k1.index(ele))+" has stood in "+str(i+1)+" place in overall with a score of "+str(ele))

