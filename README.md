My algorithm to generate rational is:

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


