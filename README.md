# Probability-calculator
determines the approximate probability of drawing certain balls randomly from a hat.
import copy
import random 
class Hat:
    def __init__(self, **kwargs):
        self.kwargs = kwargs
        self.content = []
        for x , y in self.kwargs.items():
            for i in range(y):
                self.content.append(x)
        print(self.content)
    
    
   

    def draw(self, hmany):
        if hmany > len(self.content):
            balls = copy.deepcopy(self.content)
            return balls
        else:
                balls = random.sample(self.content, hmany)
        return balls

def experiment(hat, expected_ball, num_balls_drawn, num_experiments):
    m = 0
    for i in range(num_experiments):
        hat_copy = copy.deepcopy(hat)
        experiment_ball = hat_copy.draw(num_balls_drawn)
    
    
    expected_ball_list =[]
    for k,v in expected_ball:
        expected_ball_list = v * [k]
                
    if contains_ball(expected_ball_list, experiment_ball):
        m += 1
        probability = m/num_experiments
    return probability

def contains_balls(list1, list2):
    for j in list1:
        if j in list2:
            list2.remove(j)
        else:
            return False
    return True
        
        
        
hat1 = Hat(yellow=3, blue=2, green=6) 

hat1.draw(4)
