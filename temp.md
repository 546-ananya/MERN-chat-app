function isPrimeOrGetFactors(num) {
     // Handle special cases for numbers less than 2

     if (num<= 1) {
         // 1 is not prime, its only factor is 1 if (num===1) {
          return [1];
         }
          // 0 and negative numbers are
    not prime. Factors are ill-defined in this context,
     // so we return an empty array.
      return [];
       }
       
       // ---
    Primality Test --- 
    let isNumPrime=true;
    
     // 2 is the only even prime number
     if (num===2) {
        isNumPrime=true; 
    }
     // All other even numbers are not prime
    else if (num % 2===0) {
         isNumPrime=false;
    }

    // Check for odd divisors from 3 up to the square root of num
    else {
         for (let i=3; i * i <=num; i +=2) { 
             i*i<=num is equivalent to i <=Math.sqrt(num)
              if (num % i===0) {
                isNumPrime=false;
                break; // Found a factor, so
    it's not prime
            }
        }
    }
    
     // --- Return based on primality --- 
      if (isNumPrime) {\n return true;\n } else {\n
    // The number is not prime, so find all its positive factors\n let factors=[1]; // Every number has 1 as a
    factor\n\n // Iterate from 2 up to the square root of num\n for (let i=2; i * i <=num; i++) {\n if (num % i===0) {\n
    factors.push(i);\n // If i is not the square root of num (i.e., num / i is different from i),\n // then num / i is
    also a factor.\n if (num / i !==i) {\n factors.push(num / i);\n }\n }\n }\n factors.push(num); // Every number has
    itself as a factor\n\n // Use a Set to ensure all factors are unique (though the logic above mostly prevents
    duplicates)\n // and sort them in ascending order.\n return [...new Set(factors)].sort((a, b)=> a - b);\n }\n}"