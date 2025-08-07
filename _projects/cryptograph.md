---
layout: page
title: Crypto'Graph - Diffie-Hellman Key Exchange for Private Link Prediction
description: An efficient cryptographic protocol for privacy-preserving link prediction on distributed graphs
img: assets/img/diffie_hellman.png
importance: 1
category: [Crypto]
related_publications: cryptograph
published: true
giscus_comments: true
---

## The Problem: When Organizations Want to Collaborate (But Can't Share Data)

Imagine you are trying to solve a puzzle, but the pieces are scattered across different rooms, and you can't move them. That's essentially what happens when organizations want to work together on data analysis but can't share their sensitive information.

Think about it: hospitals want to collaborate on patient research, banks want to detect fraud together, or social media platforms want to recommend connections—but they all have the same problem: **they can't share their data without violating privacy laws or exposing sensitive information**.

This is where **Crypto'Graph** comes in. It's like a magical translator that lets organizations work together on data analysis without actually sharing their private graph data.

## What is Crypto'Graph?

Crypto'Graph is a cryptographic protocol that helps multiple organizations predict future connections (or "links") in their combined graph data without anyone revealing their private information.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/link_prediction.png" title="Graph Reconstruction Process" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Crypto'Graph enables privacy-preserving computation on distributed graphs while maintaining the confidentiality of individual parties' data.
</div>


## The Secret Sauce: Secure Multiparty Computation
Crypto'Graph uses something called **secure multiparty computation (MPC)**. We specifically used an efficient implementation of the Diffie-Hellman key exchange protocol to compute shared secrets between the parties.
The idea is the following:
- When two parties want to compute the number of common neighbors between two nodes, each party creates a shared secret with the other party for each of the neighbors of the two nodes.
- These shared secrets can then be counted to obtain the number of common neighbors.
- Since the shared secrets are computed using the Diffie-Hellman key exchange protocol, each party does not learn anything about the other party's data.

In our case, organizations can work together to compute the following similarity metrics between nodes:
- The number of common neighbors
- The Jaccard Similarity
- The Cosine Similarity
- The Preferential Attachment Index

## Real-World Applications: Where This Actually Matters

### Fighting Bad Data (Graph Poisoning Defense)
Imagine someone trying to trick a recommendation system by creating fake connections. Crypto'Graph can spot these fake connections without any organization having to reveal their real data. Thanks to the privacy-preserving similarity metrics, the organizations can work together to detect which nodes are less likely to connected, and spot malicious connections in the graph. 
What works for recommendation systems can also work for other applications such as:
- Fraud detection
- Social network analysis
- Cybersecurity

We tested Crypto'Graph on real-world datasets to make sure it is actually effective at identifying malicious edges introduced by various methods in the graph, and it is !

<div class="row">
    <div class="col-sm mt-3 mt-md-0 text-center">
        {% include figure.html path="assets/img/rocs.png" title=" Performance of Crypto’Graph for malicious link identification" class="img-fluid rounded z-depth-1" width="80%" %}
    </div>
</div>


### Making Better Predictions
The system also helps improve how well AI systems can classify and predict things. Think of it like this: if you're trying to predict whether someone will like a movie, having more information (from multiple sources) helps—but Crypto'Graph lets you get that extra information without anyone sharing their private data. 

## Wrapping Up: The Bottom Line

Crypto'Graph solves a real problem that affects everyone: how can we work together on data analysis without giving up our privacy? It's like having your cake and eating it too—you get the benefits of collaboration without the risks of data exposure.

The system is particularly valuable for security-sensitive applications where protecting data is crucial. As more and more of our data becomes distributed across different organizations, tools like Crypto'Graph will become essential for enabling safe collaboration.

This research was presented at the **Fourteenth ACM Conference on Data and Application Security and Privacy (CODASPY '24)** in Porto, Portugal, and represents an important step forward in both cryptography and data analysis.

---

*Want to dive deeper? Check out the full paper in the [publications section](/publications/) or access it directly through the ACM Digital Library.*
