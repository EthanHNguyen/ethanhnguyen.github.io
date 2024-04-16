---
layout: archive
title: "Resume"
permalink: /resume/
author_profile: true
redirect_from:
  - /cv
---

{% include base_path %}

Education
======
* B.S. in Computer Science, Vanderbilt University
* M.S. in Computer Science, Georgia Institute of Technology. Specialization: Machine Learning

Work experience
======

  * August 2023 - Current: Software Engineer Intern @ Capital One
    * Built a distributed orchestration system to decide 2+ million credit card applications per month using Go & AWS (DynamoDB, State Machine, Lambda, Fargate, EC2).
    * Successfully led the migration of three high-transaction microservices, averaging 2 million transactions per month, from AWS ECS EC2 to Fargate. This strategic move eliminated the need to manage the underlying operating system, resulting in annual savings of $20,000 and a significant reduction of 800 engineering hours.
    * Led development of automated end-to-end testing suite, resulting in annual savings of 2,400 engineering hours.

* Summer 2022: Software Engineer Intern @ Capital One
  * Designed and implemented an internal REST API using AWS Lambda, SQS, DynamoDB, and API Gateway
  * Built a CI/CD pipeline with Jenkins and AWS CloudFormation

* August 2020 - December 2022: Research Assistant @ Biomedical Data Representation and Learning Lab
  * Invented novel machine learning algorithms for biomedical image analysis resulting in 2 first-author publications.
  * Trained >500 models across >20 deep learning algorithms using Python, PyTorch, Linux, and Docker.

  
Skills
======
* Languages: Python, Golang, C / C++, Java, LISP
* ML Tools: PyTorch, TensorFlow, NumPy, LangChain
* Web Development: React, Vue, Node.js, Express, HTML, CSS, JavaScript
* Databases: MongoDB, DynamoDB
* Other tools: Git, Linux, Docker, Kubernetes, AWS, Agile

Publications
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>
  
Service and Leadership
======
* December 2023 - Current: Volunteer @ Capital One - Learning & Development Committee
  * Organize monthly workshops for ~2,000 software engineers.
* January 2020 - June 2023: Volunteeer
  * Vanderbilt Volunteer for Science
  * Volunteered to teach weekly hands-on science lessons to 5-8th grade students

Awards
======
* Lera Stevens Scholarship (Full-tuition scholarship to Vanderbilt University) - $280,0000
* Goldwater Scholarship - $7,500


Certifications
======
* AWS Certified Solutions Architect - Associate