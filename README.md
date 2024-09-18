# zkMIPS Private Voting System   
[Discord](https://discord.com/channels/1125877344972849232/1234942017591578715/1285798113742815263)

## Overview
The **zkMIPS Private Voting System** is a secure and anonymous voting platform built using zkMIPS, a MIPS-compatible processor that supports zero-knowledge proofs. This system ensures voter anonymity while maintaining the integrity of the voting process by leveraging zero-knowledge proofs (ZKPs) to tally votes without revealing individual voter information.

## Features
- **Anonymity:** Voters' choices remain private throughout the voting process.
- **Zero-Knowledge Proofs:** Ensures the integrity of the vote count without exposing individual votes.
- **Security:** Only registered voters can participate, and each voter can cast only one vote.
- **Transparency:** The final voting result is verifiable, and a zero-knowledge proof is provided to confirm the correctness of the tally.

## System Components
1. **Voters:**
   - Each voter registers with a public key and is assigned a unique voter ID.
   - Voters cast encrypted votes to preserve anonymity.

2. **zkMIPS Smart Contract:**
   - Manages voter registration and vote submission.
   - Tally votes using zero-knowledge proofs, ensuring no individual vote is revealed.

3. **zkMIPS Processor:**
   - Executes the smart contract, ensuring secure vote tallying and proof generation.

4. **Voting Outcome:**
   - The system generates a zero-knowledge proof of the final vote tally, ensuring the result is correct while preserving voter privacy.

## Functions

### 1. `register_voter(public_key: Address)`
Registers a voter with their public key and assigns a unique voter ID.
```leo
function register_voter(public_key: Address) {
   // Store voter's public key
   // Generate a unique voter ID
}
```
### 2. cast_vote(voter_id: Field, encrypted_vote: Field)
Allows a registered voter to cast their vote by submitting an encrypted version of their choice.
```leo
function cast_vote(voter_id: Field, encrypted_vote: Field) {
   // Verify the voter is registered and has not voted already
   // Store the encrypted vote
}
```
### 3.tally_votes() -> (proof: Proof)
Tallies the votes using zero-knowledge proofs and ensures that all votes are counted correctly without revealing any individual votes.
```
function tally_votes() -> (proof: Proof) {
   // Tally the encrypted votes
   // Generate a ZK proof that the tally is correct
   return proof;
}
```

### 4.reveal_result(proof: Proof) -> (final_result: Field)
Verifies the zero-knowledge proof and reveals the final vote tally.
```leo
function reveal_result(proof: Proof) -> (final_result: Field) {
   // Verify the proof
   // Reveal the final tally result
   return final_result;
}
```
### Workflow
 1.Voter Registration: Eligible voters are registered with their public keys and assigned unique voter IDs. This ensures that only registered voters can participate in the voting process.

 2.Casting Votes: Voters cast their votes anonymously by submitting an encrypted version of their vote using the cast_vote function. The system ensures that each voter votes only once.

 3.Tallying Votes: Once all votes have been cast, the tally_votes function aggregates the votes while maintaining voter anonymity. It generates a zero-knowledge proof that the vote tally is correct.

 4.Result Declaration: After tallying the votes, the reveal_result function verifies the zero-knowledge proof and reveals the final tally, ensuring transparency and accuracy without compromising voter privacy.

