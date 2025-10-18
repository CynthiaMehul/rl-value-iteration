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
<img width="387" height="141" alt="image" src="https://github.com/user-attachments/assets/39ef346c-b33b-49bc-b76b-4aca2ef4a5d2" />

# Success Rate for the Optimal Policy
<img width="530" height="57" alt="image" src="https://github.com/user-attachments/assets/15f5e459-4348-4046-bb6d-b49eff5be9db" />

# Optimal value function 
<img width="367" height="118" alt="image" src="https://github.com/user-attachments/assets/a56c7af8-9030-4cda-a30e-fd2f0a25f35b" />

## RESULT:
Therefore, value iteration algorithm to find optimal policy for the altered frozen lake environment is successfully implemented.
