---
layout: post
title: "Oracle vs Google Decided"
description: ""
tags: [random]
---

The Supreme Court of the United States has issued a decision for the Oracle vs Google copyright case. While they did not address whether an API could be copyrighted, they held that Google's use of the Java API was nonetheless protected under fair use.

[How the Supreme Court saved the software industry from API copyrights](https://arstechnica.com/tech-policy/2021/04/how-the-supreme-court-saved-the-software-industry-from-api-copyrights/)

In the following example we create a function called **add** that accepts two numbers, adds them together and returns the sum.

{% highlight swift %}
func add(_ number1: Int, and number2: Int) -> Int {
	return number1 + number2
}

let sum = add(5, and: 5)
print(sum)
{% endhighlight %}

This part of the function is its Application Programming Interface (API), which declares the functions name, parameter(s) and (if applicable) return type.

{% highlight swift %}
func add(_ number1: Int, and number2: Int) -> Int
{% endhighlight %}

This part of the function is its body, where we add the functions logic.

{% highlight swift %}
{
	return number1 + number2
}
{% endhighlight %}


