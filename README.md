 Voting Contract (VotingContract)

A simple smart contract for voting, built with Solidity. This contract allows an **owner** to add candidates, open or close voting, and let users cast their votes.

 Features

- **Candidate Management**: Only the contract owner can add candidates.
- **Secure Voting**: Each user can vote only once.
- **Voting Control**: The owner can enable or disable voting.
- **Transparency**: Anyone can check the number of votes each candidate has received.
- **Events Logging**: Events are triggered when a vote is cast, a candidate is added, or the voting status changes.

 Technologies Used

- Solidity `^0.8.26`
- Ethereum Smart Contracts

 Contract Functions

 `addCandidate(string memory _name) public onlyOwner`

The owner can add a new candidate to the list.

 `vote(uint256 _candidateId) public votingIsOpen`

Each user can vote for a candidate (only once).

 `setVotingStatus(bool _status) public onlyOwner`

The owner can enable or disable voting.

 `getCandidate(uint256 _candidateId) public view returns (uint256, string memory, uint256)`

Returns candidate details (ID, name, and vote count).

 `hasVoted(address _voter) public view returns (bool)`

Checks whether a user has already voted.

 `getVotingStatus() public view returns (bool)`

Displays the current voting status (open or closed).

 How to Deploy

1. Open [Remix IDE](https://remix.ethereum.org/) or use Hardhat.
2. Copy and paste the `VotingContract.sol` code into Remix.
3. Compile using Solidity `0.8.26`.
4. Deploy it on an Ethereum test network.

 Events

- `VoteCasted(uint256 indexed candidateId, address indexed voter)` – Triggered when a vote is cast.
- `CandidateAdded(uint256 indexed candidateId, string name)` – Triggered when a new candidate is added.
- `VotingStatusChanged(bool status)` – Triggered when the voting status is changed.

 Future Improvements

- Add a list of eligible voters to prevent unauthorized voting.
- Implement a function to fetch all candidates at once.
- Introduce a mechanism to prevent smart contracts from voting (`tx.origin`).

 License

This project is licensed under the MIT License.

---

Feel free to contribute or suggest improvements

