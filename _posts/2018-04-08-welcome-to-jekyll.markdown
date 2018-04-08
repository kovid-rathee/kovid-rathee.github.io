---
layout: post
title:  "Emulating lead/lag functions in MySQL"
date:   2018-04-08 13:31:31 +0530
categories: jekyll update
---

Out of the most popular relational database management systems, MySQL is the
only one which doesn't support lead/lag functionality. Lead and lag are
functions which come in handy when you have to peek into the next record while
processing the current one. You can immediately think of an example where this
would be required. We'll talk about one of the most prominent applications of
this, i.e., finding out next order date(and hence, the number of days since
last order). Here's how you find this out in MySQL:

{% highlight sql %}

select f.order_id,
       f.customer_id,
       f.price,
       f.order_date,
       f.days_since_last_order,
       f.cumulative_spends
from (
select o.order_id,
       o.customer_id,
       o.price,
       o.order_date,
       @cumulative_spending:= @cumulative_spending + o.price cumulative_spends,
       @previous_order_date previous_order_date,
       datediff(o.order_date, @previous_order_date) days_since_last_order,
       @previous_order_date:= o.order_date
from (
select 1 order_id, 242 customer_id, 1000 price, '2018-02-01' order_date union all
select 2 order_id, 242, 35 price, '2018-02-11' union all
select 3 order_id, 242, 251 price, '2018-02-12' union all
select 4 order_id, 242, 261 price, '2018-02-18' union all
select 5 order_id, 242, 215 price, '2018-02-24' union all
select 6 order_id, 242, 236 price, '2018-03-12' union all
select 7 order_id, 242, 4384 price, '2018-03-15' union all
select 8 order_id, 242, 362 price, '2018-04-03') o,
(select @cumulative_spending := 0, @previous_order_date:= null) cp
) f;

{% endhighlight %}

Here's the [SQL Fiddle]: http://www.sqlfiddle.com/#!9/9eecb/26319, in case you
work with SQL fiddle a lot.

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
