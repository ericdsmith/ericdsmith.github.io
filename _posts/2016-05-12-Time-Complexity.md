---
layout: post
title: Algorithm Time-complexity and Big-O
---

An important skill for any software developer to have is to identify which algorithm will perform better than another. The way software engineers do that is by using a mathematical notion called Big-O notation. Big-O notation gives us insight into the relationship between the time a particular algorithm takes to complete with the size of the input. The notation's pattern is a big o, O, followed by mathematical description of how the algortihm performs. Below are some examples of common algorithmic time complexities and associated sample code that might clarify this concept further.

**Constant Time - O(n)**
The way to think about this in laymans terms is that no matter how large the input, the amount of time it takes to perform this algorithm will be the same.
```js
function constantExample(array){
  return array[0];
};
```
It doesn't matter if the array you pass to the constantExample has a length of zero or a million, it will still be the same amount of time.

**Linear Time - O(n)**
The time it takes for the algorithm to complete is proportional to the size of the input. As you can see below, for every additional element in the array, it will take one operation longer to complete.
{% highlight javascript %}
function linearExample(array){
  for(var i = 0; i < array.length; i++){
    console.log(array[i]);
  }
}
{% endhighlight %}
**Quadratic Time  - O(n^2)**
For every item you add to the input size, you will have see or touch every item again. The tell tale sign (although not always) is a nested for loop. As you can see below, everytime there is an addition to the input, it requires that every item in the array be processed one more time.
{% highlight javascript %}
function bubbleSort(array){
  for(var i = 0; i < array.length; i++){
    for(var j = 0; j < array.length; j++){
      var temp = 0;
      if(array[j] > array[j + 1]){
        temp = array[j];
        array[j] = array[j + 1];
        array[j + 1] = temp;
      }
    }
  }
  return array;
}
{% endhighlight %}
**Logarithmic Time - O(log(n))**
An algorithm that has logarithmic time complexity is going to split the size that it has to process by half on every pass. Basically as you increase the input size, the increased time to complete it will reduce with each addition. 
![Logarithmic Time Complexity Graph]({{ site.url }}/img/logarithmic-time.png)
