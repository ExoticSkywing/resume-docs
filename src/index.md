---
# 语言 （可选）
lang: en
# 网页关键词和描述
keywords: Tianyi Liu's resume
description: Hi, I'm TianYi Liu 👋
# 简历标题
resume_title: Tianyi's Resume
# 应聘者姓名
name: Tianyi Liu
avatar: https://s2.loli.net/2023/10/06/c4D1jR6MfQbzhUp.png
# 联系方式
contact:
  - icon: fas fa-globe-asia
    text: My homepage
    url: https://bento.me/moyii
  # 邮箱
  - icon: fas fa-envelope
    text: akeemkeebler495@gmail.com
    url: akeemkeebler495@gmail.com
  # 教育
  - icon: fas fa-user-graduate
    text: Bachelor's Degree 
    url: 
# PDF下载链接
download:
  title: Download Resume.
  icon: fas fa-download fa-fw
  url: 

---

{% raw %}

<center>
<a href='/'>English</a> | <a href='/zh-cn/'>简体中文</a>
</center>

{% endraw %}

--------

联系：(+86）17771429857

邮箱：[akeemkeebler495@gmail.com](mailto:akeemkeebler495@gmail.com)

主页：[Homepage](https://bento.me/moyii)

教育：本科-软件工程

## About Me

---

Bonjour! I am a C/C++ engineer with 1.5 years of experience in developing and deploying popular web backend servers. I have a diverse technical skill set and my own well-refined workflow, always striving for efficiency and technical excellence. I enjoy exploring unknown territories and have experimented with various applications on both domestic and international popular operating systems. With a panoramic view of user needs and product development, I am open-minded, love to communicate, embrace new technologies, and enjoy tackling challenging problems. I am dedicated to finding like-minded individuals like you. Here you can find some of my experiences, skills, as well as ways to contact me. Looking forward to meeting you!

### Skill Tree

![https://s2.loli.net/2023/10/06/8qiG6LCdcFu2Rnh.png](https://s2.loli.net/2023/10/06/8qiG6LCdcFu2Rnh.png)

- C++11, STL, with a good understanding of OOD (Object-Oriented Design) principles. Familiarity with the RAII concept and the use of three types of smart pointers. Implementation of C++ memory pool at the low level, as well as the underlying mechanisms of polymorphism and memory layout. Knowledge in rvalue references and perfect forwarding. Proficient in developing various projects on Linux operating system, using main editor vim and next-generation vim editor neovim. Development, compilation, and debugging using GCC/G++/GDB tools. Understanding of processes/threads, thread pools, mutexes, and synchronization.
- Solid foundation in network theory and common data structures/algorithms. TCP congestion control algorithm Cubic, as well as the BBR congestion control algorithm with superior overall performance.Familiarity with Socket network programming, multiplexing techniques such as select/poll/epoll. Understanding ICMP/ARP/NAT/BGP/Shadowsocks/TCP/IP/HTTP/HTTPS protocols as well as end-to-end encryption protocol TLS/SSL/DNS protocol. Configuration of Nginx for network reverse proxying/load balancing/service discovery purposes along with npm encapsulation.

- Docker container technology including automated management using Docker Compose, writing Dockerfiles for image construction, familiarity with Docker commands. Experience in MySQL database management system; distributed transactions and cache penetration prevention strategies for Redis; solutions to prevent cache avalanche scenarios; Git version control system for collaborative development workflows.

- Planning/debugging/optimal configuration/maintenance monitoring/fault handling/data backup/log analysis/performance bottleneck analysis related work on company servers. Responsible for real-time maintenance/upgrading/improving availability/maintainability of online servers while possessing excellent documentation skills.

- Familiarity with all popular frontend frameworks/extensions/components along with basic proficiency in HTML/CSS knowledge; awareness about backend Node.js technologies; comprehensive understanding from backend to frontend technical principles; familiarity with website development process enabling independent creation/deployment of complete websites.

## Project Experience

---

### AIGC High-Performance Web Server Development

*~ August 2022 - Present*

- Project Introduction
  With the fusion of AI and graphics, generative AI has seen a rapid increase in user demand. To ensure fast response to a large number of user drawing requests and simultaneously return pre-drawn AI images, we have developed a high-performance web server using C++11 features, Epoll, and thread pool to implement the Reactor concurrency model.
- Technology Stack
  TCP, HTTP protocols; multi-processes and multi-threads; IO operations; locks; inter-process communication; C++11 syntax; programming conventions; various tools in Linux environment; version control with Git; writing Makefile and CMakeLists files.
- Technical Details
  - Implemented the Reactor concurrency model using Epoll and thread pool.
  - Utilized state machine and regular expressions for parsing HTTP request messages, capable of handling both GET and POST requests simultaneously.
  - Encapsulated char data type into vector container to create an automatically resizable buffer.
  - Implemented timing functionality based on epoll_wait to close inactive connections that exceed timeout period. Managed timers using min heap as a container.
  - Leveraged multiple threads to fully utilize multi-core CPUs. Used thread pool to avoid frequent creation/destruction of threads overheads.
  - Implemented MySQL database connection pooling using singleton pattern to reduce overheads associated with establishing/closing database connections. Realized user registration/login functionality.
  - Developed asynchronous logging system using singleton pattern and blocking queue. Recorded server runtime status.
  - Capable of handling multipart/form-data type post requests from front-end for file upload functionality.
    Generated JSON data using jsoncpp library to send file lists to front-end for displaying files and enabling downloads.

---

### AIGC Internal User Work Storage Network Disk

*~August 2022 - Present*

- Project Introduction
  - The client communicates with the server through sockfd, and the server connects to new clients through sockfd. It uses accept to communicate with the client using newfd. The main thread is responsible for assigning tasks to sub-threads, while the sub-threads handle tasks and communicate with clients. Simple commands are executed directly by the main thread, while "puts" and "gets" commands are handed over to sub-threads for execution.
- Technical Details
  - User login and password verification: Similar to salt encryption in /etc/shadow file, it uses crypt function for encryption. User accounts, passwords, and encrypted data are stored in a database. Salt value (randomly generated) consists of 8 characters. Password matching process involves the server finding the salt based on the client's username and sending it back to the client. The client encrypts its password using crypt before sending it back to match with the server's record. It should be noted that clients do not have permission to access databases directly: User | Password | Salt | Cipher

  - Logging information: This includes client request information, connection time, client operation records, and operation time; all this information is stored in a database: User | Operation | Time

  - File resumable transfer: If there is a disconnection during "gets" process on the client side, when attempting another "gets", transmission resumes from where it left off previously. Specific implementation involves if a client wants to receive a file named 'file' starting from offset position of 1000 bytes already downloaded; then they send 'gets file 1000' command to servers which starts transmitting directly from offset position of 1000 bytes onwards; similarly on receiving end at clientside also receives starting from offset position of 1000 bytes onwards.

   - Use token authentication

   - If there is no response from a connected client within 30 seconds, the descriptor will be closed.

---

### Edge search engine

*~August 2022 - Present*

- Project Introduction
  - What is an edge search engine? It's the opposite of what you get when you search on Baidu. We strive to provide results that are not in the top rankings but have better quality than those in the top rankings. These results are scattered in the corners of the World Wide Web, collecting forgotten mysteries. They are not bound by conventional search engines and embody the concept of exploring the edge. Let the edge engine take you through and reveal those hidden and fascinating wonders.
- Technology Stack
  - Web crawler framework: Scrapy
  - Backend service: C++
  - Frontend service: VueJS
  - Deployment: Docker
- Technical Details
  - Selection of crawler strategy, depth-first or breadth-first? Save crawled URLs using a certain method (such as hash-Bloom filter) to avoid duplicate crawling, perform friendly work, and comply with ROBOT protocol.
  - Web page deduplication, clean up web articles, remove impurities, extract minimal valid keywords. Then obtain Topk and compare Topk from different web pages to determine if two web pages are highly similar.
  - Evaluation of web page quality? An important indicator is PageRank algorithm from Google which aligns well with human social society.
  - Technical highlights for web page deduplication: Open-source library cppjieba word segmentation, set stop word collection, TopK algorithm (to judge webpage duplication).
  - Construction of inverted index technical highlights: unordered_map inverted hash table, TF-IDF algorithm (calculate weight) – focus on selecting keyword weights specifically IDF. How to achieve comparability and small errors for weights? Utilize Euclidean norm to normalize data after calculating IDF.

## Work Experience

---

**Dalian Yihe Network Technology Co., Ltd.** `

*`April 2022 - October 2023`*

## Education and Others

---

**Wuhan Media College - Software Engineering**

*`September 2016 - June 2021`*

**Language: English**

Proficient in reading technical documents in the field of computer science, able to adapt to an English-speaking work environment.



## Self-evaluation

---

- Actively engage in community discussions on platforms like Reddit and Discord, exchanging technical knowledge and experiences, as well as helping others with problem-solving.
- Strong interest in technology, with a strong ability to learn and a broad technical perspective. Always eager to acquire new knowledge.
- When learning a new technology, I don't find it difficult. Instead, I constantly think about how its emergence has greatly improved our productivity. For example, the GPT trend led by OpenAI has given rise to hundreds of Chinese-flavored GPTs and AIGCs within China. Some may ask if AI will replace humans. The answer is no, but those who use AI will replace those who don't. In the field of computer science, we should continuously break boundaries and not necessarily pursue new technologies but at least strive for new knowledge. By reading more, thinking more, and practicing more, we can gain fresh insights into technology, achieve innovation in products or stand out amidst multiple waves of trends by sparking new ideas.

- While constantly exploring new knowledge as an internet professional or engineer,
  knowledge management is an essential point that cannot be ignored - it serves as the core link.
  In today's information age where information is overflowing,
  how can one break free from the torrential flow while maintaining their own perspectives?
  This may require a novel way of obtaining information sources
  and an abstract system for processing information through knowledge management,
  in order to construct one's own repository of knowledge.
  Not only does this allow previously learned knowledge to be archived and quickly retrieved,
  forming a second brain that facilitates technological accumulation,
  but most importantly it also enables the creation of new content
  and writing articles that share valuable insights.
  Just like search engines: you need your unique web crawling strategy
  to gather high-quality information sources and build up a vast library of webpages.
  Only then can you share elegant and high-quality information when users need it.
  Creating a digital garden and flowing stream is a wonderful thing.
  In the face of diverse frameworks in frontend development, there is so much to learn,
  and backend development also requires continuous learning without falling behind. The only constant is change.

- Outside of work, I also enjoy: culture and arts, appreciating well-designed webpages in frontend development,
  learning from industry experts' framework technology choices, exploring iOS platform technologies,
  the fashion field, and creating short videos. If you share similar interests, feel free to contact me at the top of this page.。

## Comments

{% raw %}

<script src="https://utteranc.es/client.js"
        repo="https://bento.me/moyii"
        issue-number="18"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>


{% endraw %}
