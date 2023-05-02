Download Link: https://assignmentchef.com/product/solved-comp9021-assignment-1-general-matters
<br>
Write a program, stored in a file named superpower.py, that does the following.

<ul>

 <li>The program prompts the user for an arbitrary number of (positive or negative) integers, all provided on one line and separated by at least one space, with possibly extra spaces anywhere. The user can input no integer at all. If the input is incorrect, then the program outputs an error message and exits. These integers are meant to represent the superpower of a bunch of heroes (positive power is good, all the better that it is larger; negative power is bad, all the worse that it is smaller).</li>

 <li>Then the program prompts the user for a nonnegative integer (possibly equal to 0), nb_of_switches, at most equal to the number of integers previously input (the number of heroes). If the input is incorrect, then the program outputs another error message and exits. This number is meant to represent the number of switches (multiplication by -1) to the power of some heroes; for instance, a hero with positive power 7 can see its power switched to -7, and a hero with negative power -5 can see its power switched</li>

</ul>

to 5.

<ul>

 <li>First, the program determines the maximum overall power that can be achieved by switching the power of nb_of_switches many heroes, a given hero seeing its power being switched an arbitrary number of times (not switched at all, or switched once, or switched more than once). For instance, with the sequence (4, -3, 1, 2, -7) and nb_of_switches set to 3, the maximum overall power that can be achieved is 15; this can be done by switching -3, 1 and -7 once: 4 + 3 <em>− </em>1 + 2 + 7 = 15. For another example, with the sequence (-7, 1, 2, 3, 4) and nb_of_switches set to 5, the maximum overall power that can be achieved is 17; this can be done by switching -7 once, 1 twice, and 3 twice: 7 + 1 + 2 + 3 + 4 = 17.</li>

 <li>Second, the program determines the maximum overall power that can be achieved by switching the power of nb_of_switches many heroes, a given hero seeing its power being switched at most once (not switched at all, or switched once). For instance, with the sequence (4, -3, 1, 2, -7) and nb_of_switches set to 3, the maximum overall power that can be achieved is 15, as previously described. For another example, with the sequence (-7, 1, 2, 3, 4) and nb_of_switches set to 5, the maximum overall power that can be achieved is -3, as each power has to be switched: 7 <em>− </em>1 <em>− </em>2 <em>− </em>3 <em>− </em>4 = <em>−</em></li>

 <li>Third, the program determines the maximum overall power that can be achieved by switching the power of nb_of_switches many consecutive heroes (note that first and last heroes are not consecutive, the heroes are aligned on a line). For instance, with the sequence (4, -3, 1, 2, -7) and nb_of_switches set to 3, the maximum overall power that can be achieved is 5; this can be done by switching the power of the last 3 heroes: 4 <em>− </em>3 <em>− </em>1 <em>− </em>2 + 7 = 5. For another example, with the sequence (-7, 1, 2, 3, 4) and nb_of_switches set to 5, the maximum overall power that can be achieved is -3, as previously</li>

</ul>

described.

<ul>

 <li>Fourth, the program determines the maximum overall power that can be achieved by switching the power of arbitrarily many (possibly none) consecutive heroes. For instance, with the sequence (4, -3, 1, 2, -7), the maximum overall power that can be achieved is 17; this can be done by switching the power of the last 4 heroes: 4 + 3 <em>− </em>1 <em>− </em>2 + 7 = 11. For another example, with the sequence (-7, 1, 2, 3, 4), the maximum overall power that can be achieved is 17; this can be done by switching the power of the first hero: 7 + 1 + 2 + 3 + 4 = 17.</li>

</ul>

Here is a possible interaction:

<h1>$ python3 superpower.py</h1>

Please input the heroes’ powers: 3 5 8.5 Sorry, these are not valid power values.

<h1>$ python3 superpower.py</h1>

Please input the heroes’ powers: 3 5 8

Please input the number of power flips: 4

Sorry, this is not a valid number of power flips.

<h1>$ python3 superpower.py</h1>

Please input the heroes’ powers: 4 -3 1 2 -7

Please input the number of power flips: 3

Possibly flipping the power of the same hero many times, the greatest achievable power is 15.

Flipping the power of the same hero at most once, the greatest achievable power is 15.

Flipping the power of nb_of_flips many consecutive heroes, the greatest achievable power is 5.

Flipping the power of arbitrarily many consecutive heroes, the greatest achievable power is 11.

<h1>$ python3 superpower.py</h1>

Please input the heroes’ powers: -7 1 2 3 4

Please input the number of power flips: 5

Possibly flipping the power of the same hero many times, the greatest achievable power is 17.

Flipping the power of the same hero at most once, the greatest achievable power is -3.

Flipping the power of nb_of_flips many consecutive heroes, the greatest achievable power is -3. Flipping the power of arbitrarily many consecutive heroes, the greatest achievable power is 17.

<h1>$ python3 superpower.py</h1>

Please input the heroes’ powers: 1 2 3 4 5

Please input the number of power flips: 2

Possibly flipping the power of the same hero many times, the greatest achievable power is 15.

Flipping the power of the same hero at most once, the greatest achievable power is 9.

Flipping the power of nb_of_flips many consecutive heroes, the greatest achievable power is 9.

Flipping the power of arbitrarily many consecutive heroes, the greatest achievable power is 15.

<ol start="3">

 <li>Cable car (3 marks)</li>

</ol>

Consider the following picture of the pillars and cable that provide the structure for a cable car. Successive pillars are equidistant. The height of each pillar is indicated above it. Continuous pillars make up for a good ride if the slope does not change over the corresponding section. Here the longest good ride is between the pillar of height 25 and the pillar of height 28; it is depicted in blue. It has a length of 3 (units, whatever it is).

30          31

If one gets rid of the black pillars and keeps only the remaining (red) ones, then one can use use the latter and create a new structure (with successive pillars being equidistant) which makes up for a perfect ride, that is, good from first to last pillar:

30

It is the longest perfect ride one can obtain this way; so 5, the number of black pillars, is the minimal number of pillars to remove to build a perfect ride from the rest.

Write a program, stored in a file named cable_car.py, that performs the following task.

<ul>

 <li>The program prompts the user to input a file name. If there is no file with that name in the working directory, then the program outputs an error message and exits.</li>

 <li>The contents of the file should consist of a strictly increasing sequence of at least two strictly positive integers. Consecutive numbers are separated by at least one space, and there can be extra spaces, including empty lines, anywhere. If that is not the case then the program outputs another error message and exits.</li>

 <li>These numbers are meant to represent the heights of pillars to build a cable car structure. The program then outputs:

  <ul>

   <li>whether or not this structure makes up for a perfect ride;</li>

   <li>the length of the longest good ride;</li>

   <li>how many pillars to remove to build a perfect ride from the remaining ones.</li>

  </ul></li>

</ul>

Here is a possible interaction:

<h1>$ python3 cable_car.py</h1>

Please enter the name of the file you want to get data from: non_existent_file.txt Sorry, there is no such file.

$ cat cable_car_wrong_1.txt

6

<h1>$ python3 cable_car.py</h1>

Please enter the name of the file you want to get data from: cable_car_wrong_1.txt Sorry, input file does not store valid data.

$ cat cable_car_wrong_2.txt

6 8 10 A 12

<h1>$ python3 cable_car.py</h1>

Please enter the name of the file you want to get data from: cable_car_wrong_2.txt Sorry, input file does not store valid data.

$ cat cable_car_wrong_3.txt

0 2 4 6 8

<h1>$ python3 cable_car.py</h1>

Please enter the name of the file you want to get data from: cable_car_wrong_3.txt Sorry, input file does not store valid data.

$ cat cable_car_wrong_4.txt

0 2 4 6 6 8

<h1>$ python3 cable_car.py</h1>

Please enter the name of the file you want to get data from: cable_car_wrong_4.txt Sorry, input file does not store valid data.

$ cat cable_car_wrong_5.txt

0 2 4 6 5 8

<h1>$ python3 cable_car.py</h1>

Please enter the name of the file you want to get data from: cable_car_wrong_5.txt Sorry, input file does not store valid data.

<h1>$ cat cable_car_1.txt</h1>

5 8

11                14

<h1>$ python3 cable_car.py</h1>

Please enter the name of the file you want to get data from: cable_car_1.txt The ride is perfect!

The longest good ride has a length of: 3

The minimal number of pillars to remove to build a perfect ride from the rest is: 0

<h1>$ cat cable_car_2.txt</h1>

5

10 14 15

20 25 26 27 28                30

31

<h1>$ python3 cable_car.py</h1>

Please enter the name of the file you want to get data from: cable_car_2.txt The ride could be better…

The longest good ride has a length of: 3

The minimal number of pillars to remove to build a perfect ride from the rest is: 5 $ cat cable_car_3.txt

10 13 20 30 40 42

44 46 48 50 60 70 80 82 85 87

90 100 101 110 113 117            121

<h1>$ python3 cable_car.py</h1>

Please enter the name of the file you want to get data from: cable_car_3.txt The ride could be better…

The longest good ride has a length of: 5

The minimal number of pillars to remove to build a perfect ride from the rest is: 12

<ol start="4">

 <li>Tunnel (4 marks)</li>

</ol>

Consider the following picture of a tunnel, determined by a sequence of ceiling heights, namely, the sequence (7, 9, 6, 8, 7, 9, 8, 7, 9, 6, 8, 7, 9, 8, 7), and a corresponding sequence of floor heights, namely, the sequence (6, 2, 1, 5, 4, 3, 6, 6, 2, 1, 5, 4, 3, 6, 6). West of the tunnel, it is possible to see into the tunnel over a distance of 2 (units, whatever that is); this is depicted in blue. Inside the tunnel, it is possible to see into the tunnel over a maximum distance of 6; this is depicted in green. Note that on this picture, the heights of the blue and green segments are at the same level, but in general they could be at different levels. Also, there could be many green line segments, as there could be many parts of the tunnel where it is possible to see into the tunnel over the same maximum distance.

Write a program, stored in a file named tunnel.py, that performs the following task.

<ul>

 <li>The program prompts the user to input a file name. If there is no file with that name in the working directory, then the program outputs an error message and exits.</li>

 <li>The contents of the file should consist of exactly two lines with the same number of at last two (positive or negative) integers. Consecutive numbers are separated by at least one space, and there can be extra spaces, including empty lines, anywhere. Also, the <em>i</em>-th number of the first sequence should be strictly greater than the <em>i</em>-th number of the second sequence because at any point in the tunnel, the ceiling is above the floor. If that is not the case then the program outputs another error message and exits.</li>

 <li>The program then outputs:</li>

</ul>

<strong>– </strong>the distance over which one can see into the tunnel when looking outside the tunnel from the West; <strong>– </strong>the maximum distance over which one can see into the tunnel when being inside the tunnel.

Here is a possible interaction:

<h1>$ cat tunnel_wrong_1.txt</h1>

7

1

<h1>$ python3 tunnel.py</h1>

Please enter the name of the file you want to get data from: tunnel_wrong_1.txt Sorry, input file does not store valid data.

<h1>$ cat tunnel_wrong_2.txt</h1>

7 3

1 0 4

<h1>$ python3 tunnel.py</h1>

Please enter the name of the file you want to get data from: tunnel_wrong_2.txt Sorry, input file does not store valid data.

<h1>$ cat tunnel_wrong_3.txt</h1>

7 3 9

1 3 4

<h1>$ python3 tunnel.py</h1>

Please enter the name of the file you want to get data from: tunnel_wrong_3.txt Sorry, input file does not store valid data.

<h1>$ cat tunnel_wrong_4.txt</h1>

7 5 9

1 3 4

0 1 2

<h1>$ python3 tunnel.py</h1>

Please enter the name of the file you want to get data from: tunnel_wrong_4.txt Sorry, input file does not store valid data.

<h1>$ cat tunnel_wrong_5.txt</h1>

7 5 9              B

1 3 4              A

<h1>$ python3 tunnel.py</h1>

Please enter the name of the file you want to get data from: tunnel_wrong_5.txt Sorry, input file does not store valid data.

<h1>$ cat tunnel_1.txt</h1>

7 9 6 8

6 2 1 5

<h1>$ python3 tunnel.py</h1>

Please enter the name of the file you want to get data from: tunnel_1.txt

From the west, one can into the tunnel over a distance of 2

Inside the tunnel, one can into the tunnel over a maximum distance of 3

<h1>$ cat tunnel_2.txt</h1>

8 7 5 6 8 9 4 8 7

6 4 3 4 5 1 2 1 2

<h1>$ python3 tunnel.py</h1>

Please enter the name of the file you want to get data from: tunnel_2.txt

From the west, one can into the tunnel over a distance of 2

Inside the tunnel, one can into the tunnel over a maximum distance of 4

<h1>$ cat tunnel_3.txt</h1>

7 9 6 8 7 9 8 7 9 6 8 7 9 8 7

6 2 1 5 4 3 6 6 2 1 5 4 3 6 6

<h1>$ python3 tunnel.py</h1>

Please enter the name of the file you want to get data from: tunnel_3.txt

From the west, one can into the tunnel over a distance of 2

Inside the tunnel, one can into the tunnel over a maximum distance of 6