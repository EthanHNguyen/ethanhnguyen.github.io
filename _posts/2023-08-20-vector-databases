---
title: 'Vector Databases'
date: 2023-08-20
permalink: /posts/2023/08/vector-databsase/
tags:
---

### What are Vector Databases?

Vector databases are databases that store vectors. Their core function is semantic search — if you have an input vector, you can find the top k most similar vectors in the database. 

### Why Vector Databases?

Large language models (LLMs) are a type of generative AI that generates text. LLMs are trained on vast amounts of text data, but they have two limitations:

1. LLMs are trained on a lot of data, and compress that vast training data into their limited memory. They lose some information in this compression. 
2. LLMs do not have access to proprietary information. LLMs are only trained a publicly available data.

To fix these two issues, one popular approach has been to feed information the LLM needs into its context [1]. LLMs have “good” reasoning ability [2], and will use this context to craft a more helpful and specefic response. 

### How can they be used in business to automate process X?

Vector databases are used to give more information to LLMs outside their training data. For business, this often includes their own proprietary data. Let’s walk through a use case. 

Assume a business conduct sales through email. They hire salespersons with varying levels of abilities. The best salesperson can sell 40% more products than the average employee. As an ML engineer, we can design a system to help the average salesperson obtain the sales figure of the best salesperson. Here’s how:

The business has all the data on a customer email and how their best salesperson responds. These pairs of emails are examples that we can use. We insert these email pairs into a vector database. Now, when the business receives an email from the customer, the system can find similar email examples in the vector database, pass it into the LLM's context as examples, and ask the LLM to generate a new email to respond to the customer using these examples. 

Using this system, every salesperson in the company can be brought up to the level of the best salesperson.

### Where can I learn more?

I find LLMs and vector databases are fascinating too! There are many resources to learn more about them. Here are a few:

If you want to understand the landscape of vector databases and their technical details, checkout The Data Quarry’s series of blogs: [https://thedataquarry.com/posts/vector-db-1/](https://thedataquarry.com/posts/vector-db-1/)

If you’re interested in seeing a tutorial for this use case, the YouTube channel AI Jason has an excellent video for this: [https://www.youtube.com/watch?v=c_nCjlSB1Zk](https://www.youtube.com/watch?v=c_nCjlSB1Zk)

### Conclusion

Vector databases are used to store additional contextual information for an LLM. This can include information more specific to the problem such as sales data. It is important to note that vector databases are used for more than just LLMs.

LLMs have potential to not only automate processes but also close the skill gap between senior and junior employees. They can also help retain proprietary knowledge when senior employees leave. In business, ML systems can help automate processes and improve the productivity of their employees.

Notes:

[1] The other common approach is fine-tuning. 

[2] LLMs are known to make reasoning mistakes. It is still unclear whether current LLMs are capable of true reasoning. However, this will likely improve over time with more data and better models. Check out these research articles: [https://arxiv.org/pdf/2212.10403.pdf](https://arxiv.org/pdf/2212.10403.pdf) and [https://arxiv.org/pdf/2303.12712.pdf](https://arxiv.org/pdf/2303.12712.pdf).