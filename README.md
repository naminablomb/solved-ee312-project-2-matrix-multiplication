Download Link: https://assignmentchef.com/product/solved-ee312-project-2-matrix-multiplication
<br>
The purpose of this project is to get some experience with arrays, pointers and memory management. Mastery of these concepts is critical to C programming. Unless you really know what you’re doing with pointers and memory allocation, you are a danger to society (well, figuratively speaking, we hope). When I wrote this assignment, I presumed that you understood the mathematical construct of a Matrix, and the calculation necessary to multiply two matrices together.




<strong>Your Mission: </strong>Edit the file “Project2.cpp” and implement the functions multiplyMatrices, transposeMatrix, and multiplyMatricesPtr.




<strong>Stage 1, Matrix Multiplication: </strong>Recall the mathematical definition of a matrix product. Given an MxN matrix A (M rows and N columns), and an NxK matrix B, calculate the MxK result matrix C as follows:




Each element Cij = Ai0B0j + Ai1B1j + Ai2B2j + … + Ai(n-1)B(n-1)j




Every element of C must be computed this way. So, we’ll need two nested <strong>while </strong>loops, one for i (which goes from 0 to M, the number of rows in A), and one loop for j, (which goes from 0 to K the number of columns in B). Nested at the innermost level will be yet another <strong>while </strong>loop (I call mine the “k-loop”) which goes from 0 to N and calculates the sum for each Cij.




Your function should have these three loops, one nested inside the other. You must, however, explicitly code the function to use row-major ordering for the matrix storage. That means that Aij is stored in the location <em>a</em>[<em>i </em>* <em>a_cols </em>+ <em>j</em>] where <em>a_cols </em>is the variable holding the number of columns in A (N in the discussion above). The matrices B and C are similarly stored in the arrays <em>b</em>[] and <em>c</em>[] respectively. For your convenience, the code you are given for <em>multiplyMatrices </em>defines the variables <em>a_rows</em>, <em>a_cols</em>, <em>b_rows</em>, <em>b_cols</em>, <em>c_rows </em>and <em>c_cols </em>(well, some are parameters, others are defined as local variables, some may not be there). <strong>You may not need to use all these variables. If you decide not to use them, please delete the variable definitions. </strong>

<strong> </strong>

<strong>Stage 2, Matrix Multiplication with Dynamic Matrices:</strong> Implement function multiplyMatricesPtr that works with dynamic matrices.  Each dynamic matrix consists of an array of pointers such that each element in the array points to one row of the matrix.  (See class materials for details.)  Both the array of points, as well as each row, are dynamically allocated.  As the result of multiplyMatricesPtr function, you should return a new <strong>dynamic matrix</strong> (of appropriate size) that contains the result of multiplication. We will “free” your matrix, so if you do not allocate appropriate size (or if you change the format of the matrix), the program will crash.




<strong>Stage 3, Matrix Transpose:</strong> Implement function transposeMatrixPtr.  Same as in the previous stage, the resulting matrix should be dynamically allocated.  The format of the matrix is described in the previous stage. We will “free” your matrix, so if you do not allocate in the format that we expect the program will crash.




<h1>Testing</h1>

You may develop your code any way you like, but the final testing should be on kamek (not luigi, or any of the other 64-bit servers), using our Makefile.




<h1>FAQ</h1>

Q1: What does running ‘make’ do?

A: make, without any arguments, generates your executable called proj2.  make test generates proj2 and then executes it.




Q2: What does make clean do?

A: make clean removes all your object code and executable files (proj2), so that you can start your compilation and linking afresh.




Q3: My code is working on my machine, but not on kamek.

A: Remove the –std=c++11 flag from the Makefile wherever it appears.   Try running ‘make clean’ to remove all your generated files before running ‘make’ again.




Q4: I am seeing a warning about files being time-stamped in the future.

A: Some of the machines have a whacky clock.  kamek seems to be OK, so run your code there.




Q5:In multiplyMatricesPtr, when we allocate the matrix C=A*B, should we perform error checking to see if malloc succeeded? If it fails, should we abort the program? Or can we just assume malloc will succeed? A: Assume that malloc will succeed.




Q6: Can we get more test cases for stage 2?

A: Not from the instructors, no.  You must make your own, and you are welcome to share them on Piazza.




Q7: My gcc/g++ is not working on kamek with the Makefile.

A: In order to run the provided Makefile on the LRC servers, please log on to kamek and enter the following command:

module initadd gcc

Then log out of the server and log back in.

This will permanently update gcc and g++ on your account on the server so that they will be compatible with our Makefile.








