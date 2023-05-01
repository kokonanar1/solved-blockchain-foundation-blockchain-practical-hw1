Download Link: https://assignmentchef.com/product/solved-blockchain-foundation-blockchain-practical-hw1
<br>
<h1>Problem 1 – Hash function</h1>

The goal of this exercise is to find a preimage and collision for a hash function. We construct the hash function <em>H</em>(<em>x</em>) as the 24 least significant bits of the <em>SHA</em><sub>256 </sub>of <em>x</em>. More precisely,

<em>H</em>(<em>x</em>) := <em>SHA</em><sub>256</sub>(<em>x</em>) <em>mod </em>2<sup>24</sup><em>.</em>

For example lets have <em>m</em><sub>1 </sub>= ”<em>Salam</em>” and <em>m</em><sub>2 </sub>= ”<em>Khodahafez</em>”, therefore

<em>SHA</em><sub>256</sub>(<em>m</em><sub>1</sub>) = e6aff8d7aabcab5ae824356814a091ba2867835cd6b50e6103b95e29866732a5,

H(<em>m</em><sub>1</sub>)= 6732a5,

<em>SHA</em><sub>256</sub>(<em>m</em><sub>2</sub>) = 82129f7ea63192c88bfa22f2613e5150ce483505549ddf08399d4589e536e8ae, H(<em>m</em><sub>2</sub>) = 36e8ae.

Use websites like https://passwordsgenerator.net/sha256-hash-generator/ to check that you are generating the same hashes.

<h1>Part 1</h1>

Assume a login website only stores <em>H</em>(<em>x</em>) of passwords. Your Password is your Sharif student id. Find two other passwords <em>m</em><sub>1 </sub>and <em>m</em><sub>2 </sub>such that you can login to your account with these two passwords as well. For example if your student number is ”91234567” then you have to find two inputs <em>m</em><sub>1 </sub>and <em>m</em><sub>2 </sub>in which <em>H</em>(<em>m</em><sub>1</sub>) = <em>H</em>(<em>m</em><sub>2</sub>) = <em>H</em>(91234567).

<strong>Hint: </strong>Do not try to implement <em>SHA</em><sub>256</sub>! Use libraries in the language that you are programming with.

<strong>Submission: </strong>Create a file named ”ans.txt”. In the first line, write your student number. In the second and third line, write two strings with the described property. Compress this file and send it in Quera. <strong>No code is required for this part</strong>.

<h1>Part 2</h1>

Assume the website stores the hash of usernames as well. So every user in this website is known by a tuple (H(username),H(password)). Write a code that output two users that are identical to website.

(H(username1)=H(username2),H(password1)=H(password2),password16=password26=username16=username2) <strong>There is a time limit of 1s for the judgment of this part.</strong>

<strong>Submission: </strong>You must submit your code in the specified format. A sample has been provided. The function <em>findCollsion</em>() must return a list with four values.

<strong>Hint: </strong>A brute force approach will not get you a full score. See <a href="https://en.wikipedia.org/wiki/Birthday_problem">The Birthday Problem.</a>

<h1>Problem 2 – Computing Discrete Logarithm</h1>

In this problem, we will find an algorithm to compute discrete logarithm in, when p is a prime number such that <em>p </em>= 2<em><sup>n </sup></em>+ 1 for some <em>n</em>. More precisely, for a given prime number <em>p</em>, generator <em>g </em>and arbitrary, we want to calculate <em>x </em>such that <em>g<sup>x </sup></em>= <em>y </em>mod <em>p</em>.

Let <em>x </em>= <em>b<sub>n</sub></em>−<sub>1</sub>2<em><sup>n</sup></em><sup>−1 </sup>+ <em>b<sub>n</sub></em>−<sub>2</sub>2<em><sup>n</sup></em><sup>−2 </sup>+ <em>… </em>+ <em>b</em><sub>1</sub>2 + <em>b</em><sub>0 </sub>be the binary representation of <em>x</em>. <strong>There is a time limit of 1s for the judgment of this question</strong>

<strong>Submission: </strong>For each part, submit a code in python. The inputs and outputs are as described below. Read the input from the standard input stream (console), and write the output in the standard output stream (console).

<strong>Remark: </strong>If you get a full score in any of the three parts, you will get the scores for the parts before that.

<strong>Input: (The format of the input is the same for all three parts)</strong>

In the first line, <em>q</em>, the number of queries. Then for <em>i </em>= 0 to <em>q </em>− 1, in lines 3<em>i </em>+ 2, 3<em>i </em>+ 3, 3<em>i </em>+ 4, a prime <em>p</em>, a generator and a value y in.

<h1>Part 1</h1>

Calculate the least significant bit of <em>x</em>, i.e. <em>b</em><sub>0</sub>, for each of the queries.

<strong>Output: </strong>For each query, output the LSB of <em>x</em>, i.e. <em>b</em><sub>0</sub>, in a separate line such that <em>g<sup>x </sup></em>= <em>y </em>mod <em>p</em>.

<strong>Hint: </strong>Use.

<h1>Part 2</h1>

Calculate the 2 least significant bits of <em>x</em>, i.e. <em>b</em><sub>1</sub><em>b</em><sub>0</sub>, for each of the queries.

<strong>Output: </strong>For each query, output the 2 LSB’s of <em>x</em>, i.e. <em>b</em><sub>1</sub><em>b</em><sub>0</sub>, in a separate line such that <em>g<sup>x </sup></em>= <em>y </em>mod <em>p</em>.

<h1>Part 3</h1>

Calculate <em>x </em>for each of the queries.

<strong>Output: </strong>For each query, output <em>x </em>in a seperate line such that <em>g<sup>x </sup></em>= <em>y </em>mod <em>p</em>.

<strong>Hint: </strong>A brute force approach will not get you a full score.

<h1>Problem 3 – Merkle Tree</h1>

In this problem, we will learn how merkle trees are constructed. To do this we will first introduce padding.

<strong>Padding: </strong>We know how to construct a merkle tree when the number of files is a power of two. Now consider the case where the number of files isn’t a power of two. We need a unique way of constructing the tree. Our padding method works as it is shown in Figure 1. At each level, if the number of existing hashes are even, we construct the higher level, otherwise, we duplicate the last value. In Figure 1, the letters are real hashes, and the letters with a prime (’) are the copies of the corresponding letters.

<h1>Part 1 – Constructing Merkle Tree</h1>

Write a code that calculates the merkle root of 20 files. Use <em>SHA</em><sub>256 </sub>as the hash function. We will be using the hex format of the hashes of the files (see the example of Question 1). In the intermediate stages, concat the strings of the hashes from the level below.

19 files have been given to you in txt format. Make an 20th file named ”file20.txt” and put in the ’resource’ directory. In this file, write one sentence about yourself. Then construct a merkle tree with these 20 files (order them with the name of the files). Use the padding method explained above whenever necessary. <strong>Use the template provided.</strong>

<strong>Submission: </strong>Fill the source.py file, such that the function <em>calculate merkle root</em>() returns the hex format of the merkle root. Submit a zip file like the one provided in the sample.

Figure 1: How to pad a merkle tree to construct it.

<h1>Part 2 – Merkle Proof</h1>

In this problem we will see how the merkle tree constructed in the previous section can be used as a proof of existence of data.

<strong>Submission: </strong>Submit a code in python. The inputs and outputs are as described below. Read the input from the standard input stream (console), and write the output in the standard output stream (console).

<strong>Input: </strong>In the first 20 lines, the hahses of the 20 files is provided in hex format. In line 21, a number <em>m </em>is written which denotes the file that we want the proof for.

<strong>Output: </strong>In the first line, print the merkle root of the data provided. In the second to sixth line, provide the proof for the <em>m<sup>th </sup></em>file. Output the hashes from the leaves to the root (bottom to top). Note that an example proof has been provided in the Figure 2.

Figure 2: In this example, we want to proof the existence of the 5th file (blue box). In a real case scenario, we will send the file and the hashes in the red circles. But here we will omit sending the file and only send the hashes in the red circles.

<h1>Problem 4 – Implementing LCR Algorithm</h1>

In this problem you are going to implement LCR leader election algorithm for an asynchronous ring. You can find more details about this algorithm on Nancy Lynch, 15.1.1.

<strong>Input: </strong>Please look at the source codes which has been given to you. You will find a config.json file. It is our input. It is an array of arrays which first value of each array is the UID of corresponding node and the second one is the delay of channel which delivers message to the next node.

<strong>Output: </strong>After some amount of time each node has to write to the console that who is the leader. Remember that this is an asynchronous setting, Not only liveness is not guaranteed but also there is no termination rule for the algorithm.