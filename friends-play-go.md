### Assignment: Implement a Web API for Go Game Score Calculation

#### Overview
In this assignment, you will create a Web API that calculates the maximum number of draws that could have occurred in a series of Go games played by three friends, given their points. The API will validate if the points are consistent with a valid set of games and results. The results will be returned in JSON format. 

A player is awarded two points for winning a game, one point is awarded to each player if the game ends in a draw and zero points if they loose the game.

Go is an abstract strategy board game for two players in which the aim is to capture more territory than the opponent by fencing off empty space.

#### Requirements

1. **Endpoint Specification**:
   - Create a web endpoint `/:p1/:p2/:p3` where `p1`, `p2`, and `p3` are the scores of the three players.
   - The scores are guaranteed to be in non-decreasing order (i.e., `p1 <= p2 <= p3`).

2. **Input Constraints**:
   - The scores will be integers within the range `0` to `30`.

3. **Output**:
   - The endpoint should return a JSON object with the maximum number of draws that could have happened.
   - If the scores aren't consistent with any valid set of games and results, the endpoint should return `-1`.

4. **Validation**:
   - Ensure that the total points can be divided evenly among the number of games played.
   - Validate the consistency of the scores.

5. **Deadline**:
   - Deadline is `29.5.24`.

#### Example

For a request to `/10/10/20`:
- If valid, return:
  ```json
  {
    "max_draws": 20
  }
  ```
- If not valid, return:
  ```json
  {
    "max_draws": -1
  }
  ```

### Instructions

1. **Setup the Project**:
   - Use a web framework of your choice (e.g., Flask for Python, Express for Node.js).
   - Ensure the environment is set up with all necessary dependencies.

2. **Define the Endpoint**:
   - Create the endpoint `/p1/p2/p3` that captures three integer parameters.
   - Validate the inputs to ensure they meet the constraints.

3. **Implement the Logic**:
   - Write a function to compute the maximum number of draws or determine if the scores are invalid.

4. **Return the Response**:
   - Return the result in a JSON format as specified above.

### Submission

1. **Code Repository**:
   - Create a repository on GitHub and commit your code.
   - Ensure the repository has a clear README file with instructions on how to set up and run the project.

2. **API Documentation**:
   - Document the API endpoint, including the expected input format and possible outputs.
   - Need not be anything fancy like Swagger/OpenAPI.

3. **Testing**:
   - Include unit tests to validate the logic for various edge cases and typical use cases.

4. **Submission**:
   - Submit the GitHub repository link and ensure it is publicly accessible.


Sure, here are some sample test cases for the Go Game Score Calculation project. These test cases should help verify that your implementation correctly handles various scenarios.
### Sample Test Cases
#### Test Case 1: Basic Valid Input
**Input**: `/0/0/0`
**Expected Output**:
```json
{
  "max_draws": 0
}
```

#### Test Case 2: Simple Valid Input with Draws
**Input**: `/1/1/2`
**Expected Output**:
```json
{
  "max_draws": 2
}
```

#### Test Case 3: Valid Input with Draws
**Input**: `/3/4/5`
**Expected Output**:
```json
{
  "max_draws": 6
}
```

#### Test Case 4: No Possible Valid Game Configuration
**Input**: `/6/6/6`
**Expected Output**:
```json
{
  "max_draws": -1
}
```
## Note
In the first example, no games were played at all, so no draws could occur either.

For the second example, 
one game occured between players 1 and 3,
and one game occured between players 2 and 3
to get a maximum of 2 draws.

It's easy to see that there's no set of games achieving the scores in third example, so the answer for it is −1.

