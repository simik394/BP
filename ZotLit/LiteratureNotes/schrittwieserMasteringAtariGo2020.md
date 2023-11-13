---
zotero-key: DBQCG7LT
zt-attachments:
  - "156"
title: Mastering Atari, Go, chess and shogi by planning with a learned model
citekey: schrittwieserMasteringAtariGo2020
---
# Mastering Atari, Go, chess and shogi by planning with a learned model

[Zotero](zotero://select/library/items/DBQCG7LT) [attachment](<file:///G:/Cloud/Storage/OneDrive%20-%20Vysok%C3%A1%20%C5%A1kola%20ekonomick%C3%A1%20v%20Praze/V%C5%A0E/8/4SA231/%C4%8Cl%C3%A1nky/DeepMind-Mastering%20Atari,%20Go,%20Chess%20and%20Shogi%20by%20Planning%20with%20a%20Learned%20Model.pdf>)

> [!#fff066] Page 1
> 
> Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model
> 
> ---
> 6 tezi
> ^JST8ZF8RaJPNZN3UMp1

---

> [!#8fdef9] Page 1
> 
> Constructing agents with planning capabilities has long been one of the main challenges in the pursuit of artiﬁcial intelligence
> ^V8YIGTFFaJPNZN3UMp1

---

> [!#8fdef9] Page 1
> 
> Tree-based planning methods have enjoyed huge success in challeng-
> ^AWMG2LJIaJPNZN3UMp1

---

> [!#8fdef9] Page 1
> 
> ing domains, such as chess and Go, where a perfect simulator is available
> ^YRUPS9HXaJPNZN3UMp1

---

> [!#eb4949] Page 1
> 
> , in real-world problems the dynamics governing the environment are often complex and unknown.
> ^NP95AIVZaJPNZN3UMp1

---

> [!#7df066] Page 1
> 
> MuZero algorithm
> 
> ---
> - MuZero algorithm
> - which, by combining a tree-based search with a learned model,
> achieves superhuman performance in a range of challenging and visually complex domains, without
> any knowledge of their underlying dynamics.
> ^436YLY9VaJPNZN3UMp1

---

> [!#fff066] Page 1
> 
> MuZero
> 
> ---
> - MuZero - learns a model that, when applied iteratively,
> predicts the quantities most directly relevant to planning: the reward, the action-selection policy, and
> the value function.
> ^2QAPTPEKaJPNZN3UMp1

---

> [!#f799d1] Page 1
> 
> When evaluated on Go, chess and shogi, withoutany knowledge of the game rules, MuZero matched the superhuman performance of the AlphaZeroalgorithm that was supplied with the game rules.
> ^RPYMGYKCaJPNZN3UMp1

---

> [!#f799d1] Page 1
> 
> When evaluated on Go, chess and shogi, withoutany knowledge of the game rules, MuZero matched the superhuman performance of the AlphaZeroalgorithm that was supplied with the game rules.
> ^DQXLH3ZXaJPNZN3UMp1

---

> [!#fff066] Page 1
> 
> Planning algorithms based on lookahead search
> ^5PEGJWPJaJPNZN3UMp1

---

> [!#8fdef9] Page 1
> 
> Planning algorithms based on lookahead search have achieved remarkable successes in artiﬁcial intelligence. Human world champions have been defeated in classic games such as checkers [34], chess [5], Go [38] and poker [3, 26], and planning algorithms have had real-world impact in applications from logistics [47] to chemical synthesis [37]. However, these planning algorithms all rely on knowledge of the environment’s dynamics, such as the
> ^TC6NY3P5aJPNZN3UMp1

---

> [!#fff066] Page 1
> 
> knowledge of the environment’s dynamics
> ^ZJTNKVZUaJPNZN3UMp1

---

> [!#fff066] Page 1
> 
> Model-based reinforcement learning (RL)
> 
> ---
> - Model-based RL - aims to address this issue by first learning a model of the
> environment’s dynamics, and then planning with respect to the learned model.
> ^7XYKKFP4aJPNZN3UMp1

---

> [!#8fdef9] Page 1
> 
> Typically, these models have either focused on reconstructing the true environmental state [8, 16, 24], or the sequence of full observations [14, 20]
> ^ZE5J9KBCaJPNZN3UMp1

---

> [!#8fdef9] Page 1
> 
> However, prior work [4, 14, 20] remains far from the state of the art in visually rich domains, such as Atari 2600 games [2].
> ^UFE97EAYaJPNZN3UMp1

---

> [!#8fdef9] Page 1
> 
> Instead, the most successful methods are based on model-free RL [9, 21, 18]
> ^4U8FMG8JaJPNZN3UMp1

---

> [!#fff066] Page 1
> 
> model-free
> 
> ---
> - model-free RL – i.e. they estimate
> the optimal policy and/or value function directly from interactions with the environment. However, model-free
> algorithms are in turn far from the state of the art in domains that require precise and sophisticated lookahead, such
> as chess and Go.
> ^IS8QLVQPaJPNZN3UMp1

---

> [!#fff066] Page 2
> 
> model-based
> ^7X7TVQWYaJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> model-free
> ^I7ABVUBEaJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> Markov-decision process (MDP)
> ^2NRVFKJQaJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> MDP planning algorithms
> 
> ---
> - MDP planning algorithms - such as value iteration
> [31] or Monte-Carlo tree search (MCTS) [7
> ^QCG6NDEPaJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> Monte-Carlo tree search (MCTS)
> 
> ---
> - Monte-Carlo tree search (MCTS) - 
>  is performed
> at each timestep t, as described in A. An action at+1 is sampled from the search policy πt, which is proportional
> to the visit count for each action from the root node. The environment receives the action and generates a new
> observation ot+1 and reward ut+1. At the end of the episode the trajectory data is stored into a replay buffer.
> ^VZ7YDSILaJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> MDP
> ^TLB9ZCLWaJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> model-based
> ^Q9U7DBJ8aJPNZN3UMp2

---

> [!#8fdef9] Page 2
> 
> It has been hypothesized that deep, stochastic models may mitigate the problems of compounding error [14, 20]
> ^RLPW8NNWaJPNZN3UMp2

---

> [!#8fdef9] Page 2
> 
> However, planning at pixel-level granularity is not computationally tractable in large scale problems. Other methods build a latent state-space model that is sufﬁcient to reconstruct the observation stream at pixel level [48, 49], or to predict its future latent states [13, 11], which facilitates more efﬁcient planning but still focuses the majority of the model capacity on potentially irrelevant detail
> ^AHY2B6YTaJPNZN3UMp2

---

> [!#8fdef9] Page 2
> 
> None of these prior methods has constructed a model that facilitates effective planning in visually complex domains such as Atari; results lag behind well-tuned, model-free methods, even in terms of data efﬁciency [45]
> ^4HTJ9NCXaJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> model-based
> ^3QML5BU4aJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> end-to-end on predicting
> ^9MG2NZ93aJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> MDP
> ^XRBVSFBAaJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> value equivalence
> 
> ---
> - value equivalence -- i.e. that, starting from the same real state, the cumulative reward of a trajectory through the
> abstract MDP matches the cumulative reward of a trajectory in the real environment
> ^J3WHLJ2LaJPNZN3UMp2

---

> [!#fff066] Page 2
> 
> temporal-difference learning
> ^NPZ8PGPEaJPNZN3UMp2

---

> [!#fff066] Page 3
> 
> Monte-Carlo Tree Search
> ^HUQQKMX9aJPNZN3UMp3

---

> [!#fff066] Page 3
> 
> TreeQN
> 
> ---
> - TreeQN - 
> learns an abstract MDP model, such that a tree search over that model (represented by a tree-structured neural network)
> approximates the optimal value function
> ^G9LUUJEYaJPNZN3UMp3

---

> [!#fff066] Page 3
> 
> Value iteration networks
> 
> ---
> - Value iteration networks =
> learn a local MDP model, such that value
> iteration over that model (represented by a convolutional neural network) approximates the optimal value function.
> ^RZCYXKKHaJPNZN3UMp3

---

> [!#fff066] Page 3
> 
> Value prediction networks
> 
> ---
> - Value prediction networks - 
> are perhaps the closest precursor to MuZero: they learn an MDP model grounded
> in real actions; the unrolled MDP is trained such that the cumulative sum of rewards, conditioned on the actual
> sequence of actions generated by a simple lookahead search, matches the real environment. Unlike MuZero there
> is no policy prediction, and the search only utilizes value prediction.
> ^3V23G2R5aJPNZN3UMp3

---
