---
layout: post
title: Prove by induction is sometimes bad
category: learning
tags: 
keywords: 
---

Today in my numerical analysis homework I encounter this problem,  
<img src="https://ocf.io/~shichenh/images/induction.png"  />

I think questions like this are bad. Because I think in many real world situations, I won't have the formula that you could do induction on.  
So for that homework problem, I decided to derive the formula from scratch and I did solve it after 2 hours.  
For the easier case, addition/substraction, I expand a few terms from the linear recurrence function(f(n) = n-1 + f(n-1)).  
For multiplication/division, I have to expand a few example terms(i.e expanding f(5)) from function g(n) = n*g(n-1) + n to find out the pattern.  

