# Issues Guide

This document contains **links to recommended issues** to solve and **guidelines** on how to approach them effectively.  

- [Mentors and Issues](#mentors-and-issues)  
- [How-to Guide](#how-to-guide)  

## Mentors and Issues  

The following repositories have open issues labeled as `good-first-issue`, which are ideal for newcomers:  

### Execution Layer Specs

| Team | Lang | Mentor | Discord username | GitHub Issues | Discord |
|------|------|--------|-----------|--------------|---------|
| [**Ethereum Execution Spec (EELS)**](https://github.com/ethereum/execution-specs) | Python | SamWilsn |  samwilsn | [Good First Issues](https://github.com/ethereum/execution-specs/issues?q=state%3Aopen%20label%3AE-easy) | TBD |
| [**Execution Spec Test (EEST)**](https://github.com/ethereum/execution-spec-tests) | Python | TBD | TBD | [Good First Issues](https://github.com/ethereum/execution-spec-tests/issues) | TBD |

### Consensus Layer Specs

| Team                    | Lang   | Mentor | Discord username | GitHub Issues       | Discord/Channel |
|-------------------------|--------|--------|------------------|---------------------|---------|
| [**Ethereum Consensus Spec**](https://github.com/ethereum/consensus-specs) | Python | Jtraglia    | jtraglia              | [Good First Issues](https://github.com/ethereum/consensus-specs/issues?q=is%3Aissue%20state%3Aopen%20label%3A%22good%20first%20issue%22)   | [WiEP Discord](https://discord.com/channels/1210263494633717800/1416410663189872650)     |


### Execution Layer Clients

| Team | Lang | Mentor | Discord username | GitHub Issues | Discord/Channel |
|------|------|--------|-----------|--------------|---------|
| [**Besu (EL)**](https://github.com/hyperledger/besu) | Java | Sally | macfarla | [Good First Issues](https://github.com/hyperledger/besu/labels/good%20first%20issue) | [Besu Discord](https://discord.gg/hyperledger) # besu-contributors|
| [**Geth (EL)**](https://github.com/ethereum/go-ethereum) | Go | Csaba | cskiraly | [Good First Issues](https://github.com/ethereum/go-ethereum/issues?q=is%3Aissue%20state%3Aopen) | TBD |

### Consensus Layer Clients

| Team | Lang | Mentor | Discord username | GitHub Issues | Discord/Channel |
|------|------|--------|-----------|--------------|---------|
| [**Prysm (CL)**](https://github.com/prysmaticlabs/prysm) | Go | Potuz | potuz | [Good First Issues](https://github.com/OffchainLabs/prysm/issues) | [Prysm Discord](https://discord.gg/prysm) # 🤝-code-contributions|
| [**Lodestar (CL)**](https://github.com/ChainSafe/lodestar) | TypeScript | Matthew Keil, Phil | matthewkeil, philngo | [Good First Issues](https://github.com/ChainSafe/lodestar/labels/good%20first%20issue) | [Lodestar Discord](https://discord.com/invite/xSAwrnCWcg)  # 🖥-lodestar-developer|

---

## How-to Guide  

### **1. Understand the Repository's Architecture**  

- Read the README.md and contributor documentation.  
- Explore past PRs to see how similar issues were solved.  
- Set up the development environment following the project's setup guide.

### **2. Analyze the Issue**

- Read the issue carefully and try to fully understand what is required.  
- Check if the issue is still open and not assigned to someone else.
- Look for related issues or PRs that might provide context.
- If anything is unclear, take time to research before asking questions.  

### **3. Clarify Open Questions**

- Don't hesitate to ask for clarifications in the issue comments or the relevant Discord channel.  
- Before asking, try to troubleshoot yourself — writing down your thought process often helps.  
- Keep questions concise and specific to avoid unnecessary back-and-forth.
- Tag relevant maintainers or mentors when appropriate.

### **4. Learn the Required Tech Stack**

- If you're unfamiliar with the coding language, take a quick introductory course to understand its basics.
- For **Go**: [Tour of Go](https://tour.golang.org/), [Go by Example](https://gobyexample.com/)
- For **Rust**: [The Rust Book](https://doc.rust-lang.org/book/), [Rust by Example](https://doc.rust-lang.org/rust-by-example/)
- For **TypeScript**: [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- For **Java**: [Oracle Java Tutorials](https://docs.oracle.com/javase/tutorial/)
- For **C#**: [Microsoft C# Documentation](https://docs.microsoft.com/en-us/dotnet/csharp/)
- Use AI tools and coding assistants for a quick dive into a new language or to get explanations of unfamiliar concepts.
- Check the repository's coding style and best practices before writing your solution.

### **5. Implement Your Solution**

- Create a new branch for your issue using the pattern `issue-#` or following the project's convention.
- Write your fix while following the repository's best practices.  
- Keep your implementation clean, maintainable, and within the scope of the issue.
- Write meaningful commit messages that explain your changes.

### **6. Write and Run Tests**

- If required, write new tests to verify your changes.  
- Run the client's test suite and confirm that all tests pass before submitting your PR.
- Follow the project's testing conventions and patterns.
- Consider edge cases and potential breaking changes.

### **7. Update Documentation or Changelogs (If Required)**

- Some issues require updates to client documentation or changelogs.  
- Follow the repository's documentation style and update the relevant files if your fix introduces a new feature or modifies existing behavior.  
- Ensure the changelog reflects important modifications before opening your PR.  

### **8. Open a Pull Request**

- Open a PR using the client's template.
- Reference the issue in the PR (`Fixes #123`).
- Explain what changes you made and why.
- Include testing steps and any relevant screenshots or logs.
- Follow the PR guidelines outlined in the [GitHub Guide – Contributing to Ethereum Clients](./3-github-guide.md#contributing-to-ethereum-clients).
- Be prepared to iterate based on reviewer feedback.

### **9. Respond to Feedback**

- Monitor your PR for comments and feedback.
- Respond promptly and professionally to reviewer questions.
- Make requested changes and push updates to your branch.
- Don't take criticism personally - it's all about improving the code.
- Thank reviewers for their time and feedback.

### **10. Celebrate Your Contribution!**

- Once your PR is merged, update your progress in the [Progress Tracker](./2-progress-tracker.md).
- Share your success with the WiEP community.
- Consider contributing to more issues in the same or different clients.

## Tips for Success

- **Start Small**: Choose issues labeled as `good-first-issue` or `beginner-friendly`.
- **Be Patient**: Open source contribution can be a learning process with multiple iterations.
- **Ask for Help**: Don't hesitate to reach out to mentors, maintainers, or the WiEP community.
- **Read the Code**: Understanding the existing codebase is crucial for making good contributions.
- **Test Thoroughly**: Make sure your changes work and don't break existing functionality.
- **Stay Engaged**: Participate in discussions, help others, and stay active in the community.

If you have any questions, feel free to ask in the [WiEP Discord](https://discord.com/invite/JvEVfKBY6W) study-group channel or the relevant client's Discord server.
