Download Link: https://assignmentchef.com/product/solved-csci964-assignment1-mlps
<br>
This assignment is intended to provide basic experience in writing neural network applications and conducting classification experiments with mlps. After having completed this assignment you should know how to implement a back propagation multi-layer neural network which can be used for a variety of classification tasks. <strong> </strong>

<strong>Preliminaries:</strong>

Read through the lecture notes on back propagation neural networks, paying particular attention to the feed forward classification algorithm and the back propagation learning algorithm. To assist with this assignment a 2 layer back propagation neural network written in C++ is provided in the file mlp.cpp. Please study this program in context with the lecture notes so that you thoroughly understand its operation. A number of training data files are also provided for you to experiment with. Make note of how the mlp’s parameters are read from the data file. Before commencing any coding, compile and run the given MLP with the data to confirm that it works. You should notice that the mlp is able to converge on some of the data sets with relatively low error rates but on other datasets the 2 layer mlp performs poorly.

<strong>Assignment Specification: </strong>

Your main task in this assignment is to implement selectable ordering of the training data and make the net more powerful by enabling the mlp to be configured as a 2, 3 or 4 layer mlp with a specified number of neurons in each layer and to use the mlp to classify all the given data. You are to also provide a test function so that the mlp can learn training data and be tested with different test data. For this assignment you can write and compile your code on PC or UNIX platforms. To complete this assignment it is recommended you follow the steps below.

<strong>Step 1: </strong> To improve mlp training, implement an option for providing selectable ordering of the training data. The “Ordering” parameter should be added to the definition header of the training data files after ObjErr. e.g.:

. . .

Mtm1: 1.2

Mtm2: 0.4

ObjErr: 0.005 Ordering: 1 . . .

“<strong>Ordering</strong>” determines which training pattern is selected each training iteration (epoch). The options are:

<ul>

 <li><strong>Fixed</strong> Always uses the same given order of training patterns.</li>

 <li><strong>Random</strong> Make completely different (random) order each iteration (i.e. new permutation).</li>

 <li><strong>Random Swap </strong>Random permutation at start. After each epoch, two random patterns are exchanged. <strong>3, 4 . .  Random N for i=0; i&lt;(N-1); i++ </strong></li>

</ul>

<strong>                                                S</strong>elect a random pattern.

<strong>                                </strong>If it was wrongly classified last time use it   if no wrong pattern was selected choose use the first one.

Tip: Try using an index array to rearrange the selection order, or to select the next pattern.

<strong>Step 2: </strong>Implement 3 and 4 layer back propagation neural network procedures by modifying the code in mlp.cpp. To do this rename the TrainNet() function to TrainNet2() and make modified copies of this function (named: TrainNet3() and TrainNet4()) with 3 and 4 layers respectively. Then incorporate a switch statement into your code so that the appropriate TrainNet() function is invoked according to the data specs. Test your completed code on the provided data and ensure that the mlp configuration in the data files (ie the number of layers, number of neurons, etc) is being complied with.  <strong>       </strong>

<strong>Step 3: </strong> Write a TestNet() function that tests the mlp’s performance by using the mlp trained with the training data to classify the test data in the data files and report the error rate. A typical run of you mlp should look like:

NetArch: IP:8 H1:5 OP:1

Params:  LrnRate: 0.6  Mtm1: 1.2  Mtm2: 0.4

Training mlp for 1000 iterations:

#       MinErr      AveErr      MaxErr     %Correct

1:     0.000006    0.077862    0.713725    19.0373

2:     0.000000    0.072893    0.673643    17.1607

3:     0.000018    0.072357    0.670814    16.9976

4:     0.000002    0.071879    0.669441    16.9976

5:     0.000012    0.071394    0.668451    16.8072

6:     0.000005    0.071004    0.667836    17.0247

7:     0.000003    0.070734    0.667509    17.2151

8:     0.000047    0.070535    0.667491    17.4055

. . . .

1000:     0.000126    0.001256    0.008060     5.1607

Testing mlp:

MinErr      AveErr      MaxErr     %Correct

0.001126    0.008256    0.015060    10.1607




End of program.

<strong>Step 4:  </strong> Your task here is to devise various back-propagation neural network of minimum size, (in terms of the number of neurons in the mlp), that can correctly classify the Two Spiral Problem (data1.txt) and the other data sets associated with Problems 2 and 3 (see below). Note: the data for problems 2 and 3 may need extra work, like normalizing the data, dividing it into training and test data and adding the mlp header information.  You should experiment with various mlps with variations in the numbers of layers, number of neurons in each layer, parameters (eg learning rate, momentum) and the number of training iterations. If you are unable to classify all the data correctly then your final mlp configuration should be a best case compromise between size and performance. For each data set you should write a report comprised of the following information:

<ul>

 <li>A brief description of the problem.</li>

 <li>A progress report of the various mlps (at least 3 mlps) that you experimented with including any parameter changes you made and the results that were achieved. Try running each mlp a few times to determine if the problem has local minimums. If so state this in the report and see if this can be avoided by increasing the momentum. You should also indicate the approximate architecture that you think is most suited for the problem and how long and the number of iterations this takes to learn the data. (eg “ . . . the best mlp for the problem appears to be a network with a large number of hidden layers with few nodes in each layer. . . ”).</li>

</ul>

Use graphs if you think this is helpful in understanding the performance differences of the various mlps.

<ul>

 <li>Report on the final mlp that you consider is either the one that classifies all the data correctly or is a best case compromise between size and performance. Provide a description of the final mlp architecture together with a drawing of the mlp. Also provide a graph showing the iterations vs error rate. (Note: for binary classification problems, the error rate should indicate the percentage of patterns correctly classified on the training and test data.)</li>

 <li>Write a brief summary of the final mlp’s performance. Was the final mlp able to learn all the training data and classify the test data correctly? If not why not? Are there local minimums with this mlp?</li>

</ul>

<strong>Submit: </strong>




<u>Neatly print your reports and code (i.e. first the reports then the C++ code) on A4 pages with an appropriate cover</u> <u>sheet and hand it in during the lecture on the 22</u><sup>nd</sup><u> of March.</u> Make sure your reports and code is correctly formatted and titled. (<u>Marks will be deducted for untidy or incorrectly formatted work.</u>) To avoid formatting problems with your code, use 2 or 3 spaces instead of tabs to indent your code and use courier font.

Also submit your source code in the file mlp.cpp via the submit facility on UNIX ie:

$ submit -u login -c CSCI964 -a 1 mlp.cpp

where ‘login’ is your UNIX login ID.




Note: Failure of your code to compile may attract zero marks. Code or reports considered to be the same due to copying will attract zero marks.  <u>To receive full marks for your assignment your program must run on the unix</u> <u>machines at uow</u>. You may also be requested to demonstrate your program if the testing of your program proves to be ineffective. Marks will be awarded for correct design, implementation and style.  An extension of time for the assignment submission or demonstration may be granted in certain circumstances.  Any request for an extension of the submission deadline or demonstration time limit must be made to the Subject Coordinator before the submission deadline.  Supporting documentation must accompany the request for any extension.  Late assignment submissions without granted extension will be marked but the mark awarded will be reduced by 1 mark for each day late.

Assignments will not be accepted if more than five days late.




<h1>Description of Data</h1>




<strong>Problem 1 – Two Spiral Problem </strong>(1-SpiralData1.txt)

The two-spiral <strong>problem</strong> can be described as a two class problem where each class is an inter twined spiral on a two dimensional plane. This is a classical example of a non-linear data problem. With this problem it is impossible to separate two spirals coiling around each other with a linear classification method so this problem requires a multiplayer neural network to solve. The spiral data considered here is comprised of 194 training pattern and 194 test patterns. The output classes are represented as 0 and 1. To classify the data any output from the net less than or equal to 0.5 can be considered as belonging to class 0 else the output can be considered to belong to class 1.




Note: The spiral data file also has the mlp header info needed to run the data on an mlp. The training and test data are the same data. You should adjust the mlp parameters to achieve the best learning result.

<strong> </strong>Problem 2 – Abalone Age Problem (data2.txt)

This problem is about predicting the age of abalone from physical measurements. The age of abalone can be determined by cutting the shell through the cone, staining it, and counting the number of rings through a microscope. As this is a boring and time-consuming task it would be better if other measurements can be taken and used to predict the age. The following attributes have been taken from abalone specimens to form the training and test data.




<table width="437">

 <tbody>

  <tr>

   <td width="192">Name                     Data Type</td>

   <td width="48">Meas.</td>

   <td width="48"> </td>

   <td width="149">Description</td>

  </tr>

  <tr>

   <td width="192">—-                           ———</td>

   <td width="48">—–</td>

   <td width="48"> </td>

   <td width="149">———–</td>

  </tr>

  <tr>

   <td width="192">Sex                         nominal</td>

   <td width="48"> </td>

   <td width="48"> </td>

   <td width="149">M=0, F=1, and I=2 (infant)</td>

  </tr>

  <tr>

   <td width="192">Length                   continuous</td>

   <td width="48">mm</td>

   <td width="48"> </td>

   <td width="149">Longest shell measurement</td>

  </tr>

  <tr>

   <td width="192">Diameter               continuous</td>

   <td width="48">mm</td>

   <td width="48"> </td>

   <td width="149">perpendicular to length</td>

  </tr>

  <tr>

   <td width="192">Height                   continuous</td>

   <td width="48">mm</td>

   <td width="48"> </td>

   <td width="149">with meat in shell</td>

  </tr>

  <tr>

   <td width="192">Whole weight      continuous</td>

   <td width="48">grams</td>

   <td width="48"> </td>

   <td width="149">whole abalone</td>

  </tr>

  <tr>

   <td width="192">Shucked weight  continuous</td>

   <td width="48">grams</td>

   <td width="48"> </td>

   <td width="149">weight of meat</td>

  </tr>

  <tr>

   <td width="192">Viscera weight  continuous</td>

   <td width="48">grams</td>

   <td width="48"> </td>

   <td width="149">gut weight (after bleeding)</td>

  </tr>

  <tr>

   <td width="192">Shell weight         continuous</td>

   <td width="48">grams</td>

   <td width="48"> </td>

   <td width="149">after being dried</td>

  </tr>

  <tr>

   <td width="192">Rings                     integer</td>

   <td width="48"> </td>

   <td width="48"> </td>

   <td width="149">+1.5 gives the age in years</td>

  </tr>

 </tbody>

</table>




Note: the Rings attribute has been normalized between 0..1 to suit mlp learning and is the output the mlp will try to learn. Thus our data here is comprised of 8 inputs and one output




<h2>Problem 3 – SPECT Heart Diagnosis Problem (data3.txt)</h2>

This dataset describes diagnosing of cardiac Single Proton Emission Computed Tomography (SPECT) images. Each of the patients is classified into two categories: normal = 0 and abnormal = 1. The database of the SPECT image sets (from patients) was processed to extract 44 features that summarize the original SPECT images. The learning task is to learn to predict the diagnosis from the 44 image features.