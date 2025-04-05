# WHAT'S INSIDE THE FOLDER
In the folder i have two C files, one for handling the vector sum (gives the sum as output on the terminal) while the second one generate a .txt file containig the d values. Lastly the .py file is to analyse the .txt
file, it will print the mean and the standard deviation of the input file.

# ARE THE THREE RESULTS THE SAME? WHY?
In the code i wrote, at the end of the process all the three different results are printed and all the three are -0.5 (obviously incorrect). Honestly i thought that at least the third method wuold work right
and maybe it should and i made some mistake but i really don't know were it is. What i expect is that such big numbers are introducing errors bigger than the 1 and -0.5 so that in the end you get completely wrong
answer from the code. Anyway changing the order of the numbers in the sum also change the result, in particular if i fistly sum the two big numbers and lastry the two small numbers i get the correct result and this is 
valid for all the three cases.

# D TESTING
For testing that the vector d is correct, after the sum i calculated the mean and the standard deviation knowing that the correct result should be respecivelly 0 and sqrt(2). In the first case i used 1000 elements 
inside the arrays and the results were close but not exactly them. For higher values of N (100000) the output was a mean of 0.00-something and standard deviation 1.41-something. With these numbers i was confident. I 
also tried to make a graph of d plotting the distribution but i'm missing the correct python library and the console gives me an error when i try to download it so i'm not sure how to proceed.  
