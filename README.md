Download Link: https://assignmentchef.com/product/solved-cpe431-homework-4
<br>
<strong>1.0          &lt; 4.3&gt; </strong>For the problems in this exercise, assume that there are no pipeline stalls and that the breakdown of executed instructions is as follows<strong>:  </strong>

<table width="461">

 <tbody>

  <tr>

   <td width="58">add</td>

   <td width="58">addi</td>

   <td width="58">slt</td>

   <td width="58">beq</td>

   <td width="58">lw</td>

   <td width="58">sw</td>

   <td width="58">jump</td>

   <td width="58">and</td>

  </tr>

  <tr>

   <td width="58">20 %</td>

   <td width="58">10 %</td>

   <td width="58">3 %</td>

   <td width="58">20 %</td>

   <td width="58">25 %</td>

   <td width="58">12 %</td>

   <td width="58">5 %</td>

   <td width="58">5 %</td>

  </tr>

 </tbody>

</table>

In what fraction of all cycles is the input of the sign-extend circuit needed? What is the circuit doing in cycles in which the input is not needed?

<strong> </strong>

<strong>2.0</strong>          <strong>&lt;4.4&gt;</strong> In this exercise we examine in detail how an instruction is executed in a single-cycle datapath. Problems in this exercise refer to a clock cycle in which the processor fetches the following instruction word:

0000 0000 0000 1100 0001 1011 0000 0000

Assume that data memory is all zeros and that the processor’s registers have the following values at the beginning of the cycle in which the above instruction word is fetched.

<table width="480">

 <tbody>

  <tr>

   <td width="48">r0</td>

   <td width="48">r1</td>

   <td width="48">r2</td>

   <td width="48">r3</td>

   <td width="48">r4</td>

   <td width="48">r5</td>

   <td width="48">r6</td>

   <td width="48">r8</td>

   <td width="48">r12</td>

   <td width="48">r31</td>

  </tr>

  <tr>

   <td width="48">0</td>

   <td width="48">-1</td>

   <td width="48">2</td>

   <td width="48">-3</td>

   <td width="48">-4</td>

   <td width="48">10</td>

   <td width="48">6</td>

   <td width="48">8</td>

   <td width="48">2</td>

   <td width="48">-16</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong>2.0.1         </strong>What are the outputs of the sign-extend and the jump “Shift left 2” unit (near the top of Figure

4.24) for this instruction word?

<strong> </strong>

<strong>2.0.2      </strong>For the ALU and the two add units, what are their data input values?

<strong> </strong>

<strong>3.0          &lt; 4.5&gt; </strong>In this exercise, we examine how pipelining affects the clock cycle time of the processor. Problems in this exercise assume that individual stages of the datapath have the following latencies:

<table width="432">

 <tbody>

  <tr>

   <td width="86">IF</td>

   <td width="86">ID</td>

   <td width="86">EX</td>

   <td width="86">MEM</td>

   <td width="86">WB</td>

  </tr>

  <tr>

   <td width="86">280 ps</td>

   <td width="86">250 ps</td>

   <td width="86">320 ps</td>

   <td width="86">330 ps</td>

   <td width="86">250 ps</td>

  </tr>

 </tbody>

</table>




Also, assume that instructions executed by the processor are broken down as follows:

<table width="346">

 <tbody>

  <tr>

   <td width="86">alu</td>

   <td width="86">beq</td>

   <td width="86">lw</td>

   <td width="86">sw</td>

  </tr>

  <tr>

   <td width="86">35%</td>

   <td width="86">15%</td>

   <td width="86">25%</td>

   <td width="86">25%</td>

  </tr>

 </tbody>

</table>




<strong>3.0.1     </strong>What is the clock cycle time in a pipelined and non-pipelined processor?

<strong> </strong>

<strong>3.0.2      </strong>Assuming there are no stalls or hazards, what is the utilization of the data memory?

<strong> </strong>

<strong>3.0.3      </strong>Instead of a single-cycle organization, we can use a multi-cycle organization where each instruction takes multiple cycles but one instruction finishes before another instruction is fetched. In this organization, an instruction only goes through stages it actually needs (e.g. ST

CPE 431/531                                                                     Homework #4                                                                           Fall 2020

only takes 4 cycles because it does not need the WB stage). Compare clock cycle times and execution times with single cycle, multi-cycle, and pipelined organization.

<strong> </strong>

<strong>4.0</strong>          <strong>&lt;4.5&gt;</strong> In this exercise, we examine how data dependences affect execution in the basic 5-stage pipeline described in Section 4.5. Problems in this exercise refer to the following sequence of instructions:




<ul>

 <li>or $t0, $s2, $t0</li>

 <li>and $t0, $t0, r4 (3) sw   $t0, 24($s6)</li>

 <li>lw $t5, 12($s6)</li>

 <li>sub $t0, $t5, $t1</li>

</ul>




Also, assuming the following cycle times for each of the options related to forwarding:

<table width="529">

 <tbody>

  <tr>

   <td width="148">Without Forwarding</td>

   <td width="148">With Full Forwarding</td>

   <td width="234">With ALU-ALU Forwarding Only</td>

  </tr>

  <tr>

   <td width="148">250 ps</td>

   <td width="148">300 ps</td>

   <td width="234">290 ps</td>

  </tr>

 </tbody>

</table>

Assume there is no forwarding in this pipelined processor. Indicate hazards and add nop instructions to eliminate them.

<strong> </strong>

<strong>5.0          </strong>Consider the following loop.

<strong>Loop</strong>:  lw    $t0, 0($t1)        and   $s6, $s2, $t1        lw    $t9, 0($t0)        lw    $t8, 0($s6)

beq   $t8, $t9, loop

Assume that perfect branch prediction is used (no stalls due to control hazards), that there are no delay slots, and that the pipeline has full forwarding support. Also, assume that many iterations of this loop are executed before the loop exits.

<strong>                </strong>Show a pipeline execution diagram for the third iteration of this loop, from the cycle in which we fetch the first instruction of that iteration up to (but not including) the cycle in whch we can fetch the first instruction of the next iteration. Show all instructions that are in thepipeline during the cycles (not just the third iteration).

<strong> </strong>