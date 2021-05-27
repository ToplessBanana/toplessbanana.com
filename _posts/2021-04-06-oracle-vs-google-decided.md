---
layout: post
title: "Oracle vs Google Decided"
description: ""
tags: [random]
---

The Supreme Court of the United States has issued a decision for the Oracle vs Google copyright case. While they did not address whether an API could be copyrighted, they held that Google's use of the Java API was nonetheless protected under fair use.

[Ars Technica](https://arstechnica.com/tech-policy/2021/04/how-the-supreme-court-saved-the-software-industry-from-api-copyrights/) explains the decision in greater detail but I'd like to focus on the difference between declaration versus implementation code, and what this decision means for everyday developers.

In the following example we create a function called **add** that accepts two numbers, adds them together and returns the sum.

{% highlight swift %}
func add(_ number1: Int, plus number2: Int) -> Int {
	return number1 + number2
}

let sum = add(5, plus: 5)
print(sum)
{% endhighlight %}

This part of the function is its Application Programming Interface (API), which declares the functions name, parameter(s) and (if applicable) return type.

{% highlight swift %}
func add(_ number1: Int, plus number2: Int) -> Int
{% endhighlight %}

This part of the function is its body, where we add the functions logic.

{% highlight swift %}
{
	return number1 + number2
}
{% endhighlight %}

Regardless of the implementation code in the functions body, it's common for products to copy a functions declaration (API), making it easier for developers to adopt.

Had the Supreme Court decided in Oracle's favor, all declaration code would need to be unique to avoid potential litigation. Personally, I don't want a future where my projects look like this.

{% highlight swift %}
func add307c234bcab9(_ number1: Int, plus number2: Int) -> Int {
	return number1 + number2
}

let sum = add307c234bcab9(5, plus: 5)
print(sum)
{% endhighlight %}
