<b>1.ToDo</b>
<p>
Compute the difference between 2014 and the year you started at this
university and divide this by the difference between 2014 and the year
you were born. Multiply this with 100 to get the percentage of your life
you have spent at this university. Use brackets if you need them.
</p>
    ((2016-2015)/(2016-1996))*100

    ## [1] 5

<b>2.ToDo</b>
<p>
Repeat the previous ToDo, but with several steps in between. You can
give the variables any name you want, but the name has to start with a
letter.
</p>
    a= ((2016-2015)/(2016-1996))*100
    a

    ## [1] 5

To remove the value stored in a rm(a)

<b>3.ToDo</b>
<p>
Compute the sum of 4, 5, 8 and 11 by first combining them into a vector
and then using the function sum
</p>
    sum(4,5,8,11)

    ## [1] 28

It prints the sum of the vector

<b>4.ToDo </b>
<p>
Plot 100 normal random numbers
</p>
    plot(rnorm(100))

![](yas_files/figure-markdown_strict/unnamed-chunk-4-1.png)<!-- -->

<b>5.ToDo</b>
<p>
Find help for the sqrt function
</p>
    help(sqrt)

    ## starting httpd help server ...

    ##  done

<b>6.ToDo</b>
<p>
Make a file called firstscript.R containing Rcode that generates 100
random numbers and plots them, and run this script several times.
</p>
    plot(rnorm(100))

![](yas_files/figure-markdown_strict/unnamed-chunk-6-1.png)<!-- --> To
run the whole script multiple times, we can press Ctrl + Shift + S

<b>7.ToDo</b>
<p>
Put the numbers 31 to 60 in a vector named P and in a matrix with 6 rows
and 5 columns named Q. Tip: use the function seq. Look at the different
ways scalars, vectors and matrices are denoted in the workspace window.
</p>
    P = seq(from=31, to=60, by=1)
    Q= matrix(P,ncol = 5, nrow = 6)
    P

    ##  [1] 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53
    ## [24] 54 55 56 57 58 59 60

    Q

    ##      [,1] [,2] [,3] [,4] [,5]
    ## [1,]   31   37   43   49   55
    ## [2,]   32   38   44   50   56
    ## [3,]   33   39   45   51   57
    ## [4,]   34   40   46   52   58
    ## [5,]   35   41   47   53   59
    ## [6,]   36   42   48   54   60

P displays a sequence of numbers from 31 to 60 incremented by 1 Q
creates a matrix from P with 5 columns and 6 rows

<b>8. ToDo</b>
<p>
Make a script file which constructs three random normal vectors of
length 100. Call these vectors x1, x2 and x3. Make a data frame called t
with three columns (called a, b and c) containing respectively x1, x1+x2
and x1+x2+x3. Call the following functions for this data frame: plot(t)
and sd(t). Can you understand the results? Rerun this script a few
times.
</p>
    x1=c(rnorm(100))
    x2=c(rnorm(100))
    x3=c(rnorm(100))
    t= data.frame(a=x1,b=x1+x2,c=x1+x2+x3)
    plot(t)

![](yas_files/figure-markdown_strict/unnamed-chunk-8-1.png)<!-- -->

    sd(t$a+t$b+t$c)

    ## [1] 3.167694

The first part of the graph shows us the graph of a and then for b and c
which is x1 and x1+ x2 and x1+x2+x3

<b>9.ToDo</b>
<p>
Add these lines to the script file of the previous section. Try to find
out, either by experimenting or by using the help, what the meaning is
of rgb, the last argument of rgb, lwd, pch, cex.  
</p>
    plot(t$a, type="l", ylim=range(t),lwd=3, col=rgb(1,0,0,0.3))
    lines(t$b, type="s", lwd=2,col=rgb(0.3,0.4,0.3,0.9))
    points(t$c, pch=20, cex=4,col=rgb(0,0,1,0.3))

![](yas_files/figure-markdown_strict/unnamed-chunk-9-1.png)<!-- --> The
rgb() function creates colors according to the given intensities of the
colors red, blue and green.

<b>10.ToDo</b>
<p>
Compute the mean of the square root of a vector of 100 random numbers.
What happens?

</p>
    sqrt(mean(rnorm(100)))

    ## [1] 0.1712113

<b>11.ToDo</b>
<p>
Make a file called tst1.txt in Notepad from the example in Figure 4 and
store it in your working directory. Write a script to read it, to
multiply the column called g by 5 and to store it as tst2.txt.
</p>
    d = data.frame(g = c(3,4,5),h = c(12,43,54))
    write.table(d, file="tst1.txt", row.names=FALSE)
    d2 = read.table(file="tst1.txt",header=TRUE)
    a=d2$g*5;
    write.table(a, file="tst2.txt", row.names=FALSE)

This creates a dataframe d with 2 variables called g and h Then in the
next line we are creating a text file with the data stored in it The
line after that we are reading the data from that file In the last we
are multiplying the column g by 5, We are callilng g with $g

<b>12.ToDo</b>
<p>
Make a graph with on the x-axis: today, Sinterklaas 2014 and your next
birthday and on the y-axis the number of presents you expect on each of
these days. Tip: make two vectors first.

</p>
    date1=strptime( c("20160127","20161003"),format="%Y%m%d")
    present=c(10,6)
    date1

    ## [1] "2016-01-27 EST" "2016-10-03 EDT"

    present

    ## [1] 10  6

<b>13.ToDo</b>

<p>
Make a vector from 1 to 100. Make a for-loop which runs through the
whole vector. Multiply the elements which are smaller than 5 and larger
than 90 with 10 and the other elements with 0.1.
</p>
    vector=seq(from=1, to=100, by=1)
    s=c()
    for(i in 1:100)
    {
      if(vector[i]<5)
      {
        s[i]=vector[i]*5;
      }
      else if(vector[i]>90)
      {
        s[i]=vector[i]*10;
      }
      else
      {
        s[i]=vector[i]*0.1;
      }
    }
    s

    ##   [1]    5.0   10.0   15.0   20.0    0.5    0.6    0.7    0.8    0.9    1.0
    ##  [11]    1.1    1.2    1.3    1.4    1.5    1.6    1.7    1.8    1.9    2.0
    ##  [21]    2.1    2.2    2.3    2.4    2.5    2.6    2.7    2.8    2.9    3.0
    ##  [31]    3.1    3.2    3.3    3.4    3.5    3.6    3.7    3.8    3.9    4.0
    ##  [41]    4.1    4.2    4.3    4.4    4.5    4.6    4.7    4.8    4.9    5.0
    ##  [51]    5.1    5.2    5.3    5.4    5.5    5.6    5.7    5.8    5.9    6.0
    ##  [61]    6.1    6.2    6.3    6.4    6.5    6.6    6.7    6.8    6.9    7.0
    ##  [71]    7.1    7.2    7.3    7.4    7.5    7.6    7.7    7.8    7.9    8.0
    ##  [81]    8.1    8.2    8.3    8.4    8.5    8.6    8.7    8.8    8.9    9.0
    ##  [91]  910.0  920.0  930.0  940.0  950.0  960.0  970.0  980.0  990.0 1000.0

<b>14.ToDo</b>

<p>
Write a function for the previous ToDo, so that you can feed it any
vector you like (as argument). Use a for-loop in the function to do the
computation with each element. Use the standard R function length in the
specification of the counter. a )
</p>
    fun= function(arg1,arg2 )
    {
      vector[i]=arg1[i];
      for(i in length(vector))
      {
        
      }
    }
