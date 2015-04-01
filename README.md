My algorithm to generate rational is:

Method  0:
      valid (int n , int d){
          if( n and d are co-prime) then return true;
          return false;
      }
      
      gcd(int n , int d){
          if( n and d are co-prime) then return (n , d);
          else return gcd (n + 1 , d - 1);
      }
      
      next ( int n , int d) { // will give the next valid rational
          if( n % 2 == d % 2){ // n = numerator , d = denominator
            n++;
            if(d > 1) d--;
            if ( (n , d) is valid rational) then return (n, d);
            else return gcd (n , d);
          }
          else{
            if(n > 1) n--;
            d++;
            if ((n , d) is valid rational) then return (n, d);
            else return gcd (n , d);
          }
      }


// The only problem is, it takes too much time when i want to take first 15 element from the stream. Below 10 it does very fast. 

// The fastest method
Method1: 
 next (int n, int d){
    if( n == 1) then return (d + 1 , 1);
    else return (pred n , suc d);
 }


//slower than mathod1 but faster than method0
Method2:

next ( int n , int d) { // will give the next valid rational
          if( n % 2 == d % 2){ // n = numerator , d = denominator
            n++;
            if(d > 1) d--;
            return (n , d);
          }
          else{
            if(n > 1) n--;
            d++;
            return (n , d);
          }
      }

Note:
we can see than method1 and method2 will generate all rational unique + non-unique. 
Now we have to process further for picking the valid rational. 
