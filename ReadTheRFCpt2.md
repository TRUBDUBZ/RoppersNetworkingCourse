# Read The RFC Part 2

1. What is the TC bit?

  - The Tc (Truncated) Header Bit: indicates that truncation has occured. 
    - Truncation: In mathematics and computer science, truncation is limiting the number of digits right of the decimal point.[Wikipedia - Truncation](https://en.wikipedia.org/wiki/Truncation)
  
  - The TC bit is set in the header once a UDP packet has exceeded the maximum of 512 bytes. 

2. Would you describe the TC bit as... boolean? What is a bool?

  - Yes, the TC bit is a bool in my view because it is set regarding if something is true or false.  
  
  - True: Truncation has occured  
  - False: Truncation has not occured 
  
3. In the header of a message, how many bits from the ID field is the TC bit?

  - the TC bit is 4 bits from the ID field
