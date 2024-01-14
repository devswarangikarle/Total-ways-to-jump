# Total-ways-to-jump
A frog jumps either 1, 2, or 3 steps to go to the top. In how many ways can it reach the top of Nth step. As the answer will be large find the answer modulo 1000000007.

def count_ways_to_top(N):
    dp = [0] * (N + 1)

    dp[0] = 1
    dp[1] = 1
    dp[2] = 2

    for i in range(3, N + 1):
        dp[i] = (dp[i - 1] + dp[i - 2] + dp[i - 3]) % 1000000007

    return dp[N]

N = int(input())

result = count_ways_to_top(N)
print(result)
