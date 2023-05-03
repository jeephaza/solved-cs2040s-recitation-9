Download Link: https://assignmentchef.com/product/solved-cs2040s-recitation-9
<br>
<strong>Problem 1.              A whole lot of work to do….</strong>

Suppose you have a huge amount of work to do. To keep track of the <em>n </em>tasks, you have a big array <em>W </em>where <em>W</em>[<em>j</em>] = 0 means that task <em>j </em>has not yet been completed, and <em>W</em>[<em>j</em>] = 1 implies that task <em>j </em>has been completed.

<table width="374">

 <tbody>

  <tr>

   <td width="31">0</td>

   <td width="31">0</td>

   <td width="31">1</td>

   <td width="31">0</td>

   <td width="31">0</td>

   <td width="31">1</td>

   <td width="31">1</td>

   <td width="31">1</td>

   <td width="31">1</td>

   <td width="31">1</td>

   <td width="31">0</td>

   <td width="31">0</td>

  </tr>

 </tbody>

</table>

0       1       2       3       4       5       6       7       8       9      10     11

<strong>Figure 1: </strong>An example of <em>W</em>.

In order to help coordinate getting all the work done, you want to implement a data structure that implements the following three operations:

<table width="623">

 <tbody>

  <tr>

   <td width="100"><strong>Operation</strong></td>

   <td width="523"><strong>Behaviour</strong></td>

  </tr>

  <tr>

   <td width="100">lookup(j)</td>

   <td width="523">returns the value <em>W</em>[<em>j</em>].</td>

  </tr>

  <tr>

   <td width="100">mark(j)</td>

   <td width="523">marks task <em>j </em>as completed, i.e., sets <em>W</em>[<em>j</em>] = 1.</td>

  </tr>

  <tr>

   <td width="100">nextTask(j)</td>

   <td width="523">returns the next task ≥ <em>j </em>that is not yet completed, i.e., the next index <em>j </em>≥ 0 where <em>W</em>[<em>j</em>] = 0.</td>

  </tr>

 </tbody>

</table>

For example, for the array above (Figure 1), lookup(2) returns 1, mark(4) would change the zero to a one, and nextTask(6) would return 10.

The simplest solution, of course, is just to use the array. In that case, it is easy to implement the lookup and mark operations in <em>O</em>(1) time, but the nextTask operation may take Ω(<em>n</em>) time.

The goal in this problem is to develop data structures that provide different trade-offs in performance. For all versions, we want lookup to complete in <em>O</em>(1) time.

<strong>Problem 1.a. </strong>Design a data structure where the mark and nextTask operations complete in <em>O</em>(log<em>n</em>) time, worst-case.

<strong>Problem 1.b. </strong>Design a data structure where the mark operation runs in <em>O</em>(log<em>n</em>) <em>amortized </em>time and nextTask operation runs in <em>O</em>(1) time, worst-case.

<strong>Problem 1.c. </strong>Design a data structure where the mark operation runs in worst-case <em>O</em>(1) time and nextTask operation runs in <em>O</em>(<em>α</em>(<em>n</em>)) <em>amortized </em>time (where <em>α</em>(<em>n</em>) refers to the time complexity of the inverse Ackermann function, i.e., the amortized time for executing <em>n </em>operations on a unionfind data structure).

<strong>Problem 2.             Communist Data Structures</strong>

In this problem we will build a new type of mergeable Max-Heap. It is often useful to be able to merge data structures. For example, they can be used to build divide-and-conquer algorithms, they can be used more easily in augmenting trees, etc.

Let us define the following terms:

<table width="623">

 <tbody>

  <tr>

   <td width="170"><strong>Term</strong></td>

   <td width="453"><strong>Definition</strong></td>

  </tr>

  <tr>

   <td width="170">right spine</td>

   <td width="453">The sequence of nodes traversed in a tree if you start at a node and always go right until you find a node with no right child (which may not be a leaf).</td>

  </tr>

  <tr>

   <td width="170"><em>rightRank</em></td>

   <td width="453">The number of nodes along a right spine.</td>

  </tr>

  <tr>

   <td width="170">LEFTIST property</td>

   <td width="453">The property a tree satisfies if, for every node that has two children L and R, <em>rightRank</em>(<em>L</em>) <em>&gt;</em>= <em>rightRank</em>(<em>R</em>).</td>

  </tr>

  <tr>

   <td width="170">LEFTIST (Max) HEAP</td>

   <td width="453">A tree that satisfies both the (Max) Heap order property and the LEFTIST property.</td>

  </tr>

 </tbody>

</table>

<strong>Figure 2: </strong>Example of a LEFTIST HEAP, where the <em>rightRank </em>for each node is labelled next to it.

<strong>Problem 2.a.               </strong>What is the maximum height/depth of a LEFTIST HEAP?

<strong>Problem 2.b.      </strong>What is the maximum <em>rightRank </em>of a LEFTIST HEAP containing <em>n </em>nodes?

<strong>Problem 2.c.    </strong>Suppose you want to add a node to a LEFTIST HEAP. Where would be a good place to insert it? What is the maximum cost?

<em>Hints: </em>Think recursively! Where is an efficient place to insert it? Realise also you can always swap the left and right subtrees of a node if it does not satisfy the LEFTIST property.

<strong>Problem 2.d. </strong>Now come up with an algorithm for merging two LEFTIST HEAPs together. What is the running time?

<em>Hint: </em>Apply the same idea from part b.

<strong>Problem 2.e.               </strong>How would you implement extractMax in a LEFTIST HEAP?

<strong>Problem 2.f. </strong>How would you implement delete (and decreaseKey) efficiently in such a LEFTIST HEAP?