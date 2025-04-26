# cs771-assignment-2-solved


    **TO GET THIS SOLUTION VISIT:** [CS771 Assignment 2 Solved](https://www.ankitcodinghub.com/product/cs771-solved-3/)

    ---

    📩 **If you need this solution or have special requests:**  
    **Email:** ankitcoding@gmail.com  
    📱 **WhatsApp:** +1 419 877 7882  
    📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

    *We deliver fast, professional, and affordable academic help.*

    ---

    <h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;133176&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS771 Assignment 2 Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">
            
<div class="kksr-stars">
    
<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
    
<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>
                

<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
1 Solution 1

1.1 Theory

Figure 1: Illustration of a working ID3 algorithm

We have used the Iterative Dichotomizer decision tree algorithm which is considered one of the most robustly used algorithms for supervised machine learning classification tasks. The algorithm works by recursively partitioning the training data based on their attributes until the decision tree produces the purest splits (referred to as the leaves). ID3 uses a top-down greedy approach to build a decision tree. The tree is basically constructed from the top and the greedy approach means that at each iteration the best feature is selected to split the node.

1.2 Our approach

The decision tree constructed to solve the given Wordle-Solvr problem consists of the following components:

1.2.1 process node

• For the process node function, every non-root node present in the ID3 tree constructed is considered and passed through the get entropy function which calculates the index of the vocabulary that minimizes entropy the most or maximizes the Information Gain. This index can be used to access the most appropriate query that can be used at that step.

Preprint. Under review.

• All words from list all words list are extracted and reveal function helps to uncover the mask between the query and the required word which is stored in split dict as the key. The value of the split dict contains an array of indices that returns the given mask when queried.

get entropy

• The get entropy function iterates over all of the words present in that node (possible candidate queries) and passes the array to the function calc entropy which returns the entropy of the current node.

• Another dictionary is maintained which given the mask, corresponds to a number of queries(which when queried with the word provides that particular mask). These values are used to calculate the sum of weighted entropy after splitting the node.

• The difference of the weighted sum of entropies after splitting the node with the initialentropy calculated from the parent node gives us the information gain used to produce the best split out of all words.

(1)

where, V = possible values in Attribute A,

S = set of examples X,

Sv = subset where XA = V

• Information gain indirectly describes the mutual information between the attribute and theclass of labels S.

calc entropy

• This function simply calculates the Shannon Entropy based on the formula where p represents the probability of each class label which can be produced by the corresponding split based on their attribute.

E(p) = −p · log2(p) (2)

2 Solution 2

The entire algorithm has been implemented in the submit.py file.

2
    
