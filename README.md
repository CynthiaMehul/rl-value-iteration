# VALUE ITERATION ALGORITHM
## AIM
Implement value iteration algorithm to find optimal policy for the altered frozen lake environment.

## PROBLEM STATEMENT
Make alterations in the default frozen lake environment like changing the starting state, goal state and holes in the environment. Further find optimal policy using value iteration.

## VALUE ITERATION ALGORITHM

# Step 1:
Import required libraries for the program.
# Step 2:
Load the frozen lake environment and make changes. 
# Step 3: 
Define the value iteration function.
# Step 4:
Run the function and display the results.

## VALUE ITERATION FUNCTION
### Name: Cynthia Mehul J
### Register Number: 212223240020
```
def value_iteration(P, gamma=1.0, theta=1e-10):
    V = np.zeros(len(P), dtype=np.float64)
    while True:
      Q=np.zeros((len(P),len(P[0])),dtype=np.float64)
      for s in range(len(P)):
        for a in range(len(P[s])):
          for prob, next_state, reward, done in P[s][a]:
            Q[s][a]+=prob*(reward+gamma*V[next_state]*(not done))
      if np.max(np.abs(V-np.max(Q,axis=1)))<theta:
        break
      V=np.max(Q,axis=1)
    pi=lambda s: {s:a for s,a in enumerate(np.argmax(Q,axis=1))}[s]
    return V, pi
```

## OUTPUT:
# Optimal Policy
<img width="496" height="137" alt="image" src="https://github.com/user-attachments/assets/f8a8816d-acb6-43b7-9c0a-5bc75d36b69c" />

# Success Rate for the Optimal Policy
<img width="698" height="52" alt="image" src="https://github.com/user-attachments/assets/dc98d609-68f1-43d2-a690-c0d9e13ba2ca" />

# Optimal value function 
<img width="444" height="114" alt="image" src="https://github.com/user-attachments/assets/d7bf515c-068c-4284-a2a2-74aa24127a80" />

## RESULT:
Therefore, value iteration algorithm to find optimal policy for the altered frozen lake environment is successfully implemented.
