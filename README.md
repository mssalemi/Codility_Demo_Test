# Codility_Demo_Test
Codility Demo Test Sollution Swift 2.0
This is my code for the Colidity Demo Test is anyone is having trouble with it. On my first attempt, I was getting O(N^2)
and error for large numbers. I used the first way I thought of using a double for loop. To get O(N) I decided to only use one 
for loop, by getting the sum at the start, and going from index 0 -> Length of Array, and updating that sum accordingly.

public func solution(A : [Int]) -> Int {

    let e = -1
    
    if (A.count <= 1) {
        return e
    }
    
    var sum : Float80 = 0
    var rightSum : Float80 = 0
    var leftSum : Float80 = 0
    
    for i in 0 ... A.count-1 {
        sum += Float80(A[i])
    }
    
    for i in 0 ... A.count-1 {
        rightSum = sum - leftSum - Float80(A[i])
        if (leftSum == rightSum) {
            return i
        }
        leftSum += Float80(A[i])
    }

    return e
}
