# Step 1: Create a list to store party name, candidate name, and votes received in each constituency
constituencies = [
    {
        "name": "Constituency A",
        "candidates": [
            {"party": "Party X", "candidate": "Candidate 1", "votes": 4500},
            {"party": "Party Y", "candidate": "Candidate 2", "votes": 4700},
            {"party": "Party Z", "candidate": "Candidate 3", "votes": 4800},
        ]
    },
    {
        "name": "Constituency B",
        "candidates": [
            {"party": "Party X", "candidate": "Candidate 4", "votes": 5000},
            {"party": "Party Y", "candidate": "Candidate 5", "votes": 5100},
            {"party": "Party Z", "candidate": "Candidate 6", "votes": 4900},
        ]
    },
    {
        "name": "Constituency C",
        "candidates": [
            {"party": "Party X", "candidate": "Candidate 7", "votes": 5200},
            {"party": "Party Y", "candidate": "Candidate 8", "votes": 5300},
            {"party": "Party Z", "candidate": "Candidate 9", "votes": 5400},
        ]
    }
]

# Step 2: Calculate the total votes for each party, identify the winner in each constituency, and determine the overall election winner
total_votes = {}
overall_results = {}

for constituency in constituencies:
    print(f"\n{constituency['name']}:")
    max_votes = 0
    winner_party = ""
    
    for candidate in constituency["candidates"]:
        party = candidate["party"]
        votes = candidate["votes"]
        
        # Calculate total votes for each party
        if party in total_votes:
            total_votes[party] += votes
        else:
            total_votes[party] = votes
        
        # Identify the winner in each constituency
        if votes > max_votes:
            max_votes = votes
            winner_party = party
    
    print(f"Winner in {constituency['name']}: {winner_party} with {max_votes} votes")
    
    # Track overall results
    if winner_party in overall_results:
        overall_results[winner_party] += 1
    else:
        overall_results[winner_party] = 1

# Determine the overall election winner
overall_winner = max(overall_results, key=overall_results.get)
print(f"\nOverall Election Winner: {overall_winner} with {overall_results[overall_winner]} constituencies won")

# Step 3: Calculate vote sharing percentage and identify constituencies with close contests (vote margin < 12%)
print("\nVote Sharing Percentage and Close Contests:")
for constituency in constituencies:
    print(f"\n{constituency['name']}:")
    total_votes_constituency = sum(candidate["votes"] for candidate in constituency["candidates"])
    
    for candidate in constituency["candidates"]:
        party = candidate["party"]
        votes = candidate["votes"]
        vote_share = (votes / total_votes_constituency) * 100
        print(f"{party} ({candidate['candidate']}): {vote_share:.2f}%")
    
    # Identify close contests
    sorted_candidates = sorted(constituency["candidates"], key=lambda x: x["votes"], reverse=True)
    margin = (sorted_candidates[0]["votes"] - sorted_candidates[1]["votes"]) / total_votes_constituency * 100
    
    if margin < 12:
        print(f"Close contest in {constituency['name']} with a margin of {margin:.2f}%")

# Print total votes for each party
print("\nTotal Votes for Each Party:")
for party, votes in total_votes.items():
    print(f"{party}: {votes} votes")