# Read The RFC Part 2

## 1. What is the TC bit?

- The Tc (Truncated) Header Bit: indicates that truncation has occured.

  - Truncation: In mathematics and computer science, truncation is limiting the number of digits right of the decimal point.

- The TC bit is set in the header once a UDP packet has exceeded the maximum of 512 bytes.  
- Source: [Wikipedia - Truncation](https://en.wikipedia.org/wiki/Truncation)

## 2. Would you describe the TC bit as... boolean? What is a bool?

- Yes, the TC bit is a bool in my view because it is dependant on if something is true or false.  

```markdown
   True: Truncation has occured  

   False: Truncation has not occured 
```

## 3. What is a **bool**?

- A bool is a data type with two possible values: true or false.  
  - the name comes from the English mathematician George Boole: "boolean" or "bool" for short
  - [bool Notes: source](https://www.computerhope.com/jargon/b/boolean.htm)

## 4. In the header of a message, how many bits from the ID field is the TC bit?

- The TC bit is 4 bits from the ID field
