TOTAL_CHARS = 256
def max_distinct_char(str, n):
    count = [0]
    count=count * TOTAL_CHARS 
    for i in range(n): 
        count[ord(str[i])] += 1
    max_distinct = 0
    for i in range(TOTAL_CHARS): 
        if (count[i] != 0): 
            max_distinct += 1    
      
    return max_distinct 
  
def smallestSubDistinctChar(str): 
    n = len(str)    
    max_distinct = max_distinct_char(str, n) 
    minl = n    
    for i in range(n): 
        for j in range(n): 
            subs = str[i:j] 
            subs_length = len(subs) 
            sub_distinct_char = max_distinct_char(subs,  
                                                  subs_length)  
            if (subs_length < minl and 
                max_distinct == sub_distinct_char): 
                minl = subs_length 
  
    return minl 
str=input()
result=smallestSubDistinctChar(str)
print(result)
  
