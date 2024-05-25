### Assignment: Implement a Web API for Go Game Score Calculation

#### Overview
In this assignment, you will create a Web API that calculates the maximum number of draws that could have occurred in a series of Go games played by three friends, given their scores. The API will validate if the scores are consistent with a valid set of games and results. The results will be returned in JSON format.

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

#### Example

For a request to `/10/10/20`:
- If valid, return:
  ```json
  {
    "max_draws": 10
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
