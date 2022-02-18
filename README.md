# 3x-1AlgorythmAverage
This is an algorithm of an algorithm. It takes a range and calculates the amount of times it had to iterate until it reached the number 1 on every single number and calculates the average. It uses the 3x+1 algorithm which always eventually reaches 1.

honestly I'm surprised of how hard it is to upload a python project on Github even while using GitHub Desktop. so screwit I'll put it in the README file. Copy as you like lol

number = 0
currentIterations = 0
howManyIterationsItTook = []

rangeStart = 4
rangeEnd = 1000000

for i in range(rangeStart, rangeEnd):
    while number != 1.0:
        if currentIterations == 0: #means if we moved on to the next number, it takes the number of i instead of the number of 'number'
            if i % 2 == 0:
                number = int(i / 2)
            else:
                number = 3 * i + 1
        elif number % 2 == 0: #else it just keeps iterating and counting the iterations
            number = int(number / 2)
        else:
            number = 3 * number + 1
        currentIterations += 1
    howManyIterationsItTook.append(currentIterations)
    number = 0
    currentIterations = 0 #save and reset everything for the next number


print(sum(howManyIterationsItTook) / len(howManyIterationsItTook)) #prints the average amount of times it used one of the formulas until it reached a cycle


happy coding!
