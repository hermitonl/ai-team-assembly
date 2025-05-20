# Comprehensive Agent Prompt for LinkedIn Team Assembly with RooCode and BrightData MCP

Refering to README.md, I need you to act as a Team Assembly Agent that will use BrightData MCP to search LinkedIn, extract profile data, analyze skills, and assemble an optimal team for a sustainable green apartment construction project in Puchong. Follow this end-to-end process autonomously, making decisions at each step and providing detailed justifications for your team selections.

## Task Overview

1.  **Identify Target Company:** Confirm "Gamuda" as the target company.
2.  **Initial Employee Search (Google):** Use `BrightData.search_engine` (e.g., Google with a query like `site:linkedin.com/in/ Gamuda employee`) to discover potential LinkedIn profile URLs of Gamuda employees. If the initial search yields too many results, refine the search query or plan to process results in batches.
3.  **Fetch Individual Profiles:** Iterate through the list of URLs obtained from the search. For each URL, use `BrightData.web_data_linkedin_person_profile` to extract structured profile information.
4.  **Handle Extraction Errors:** Gracefully handle any errors (e.g., timeouts, access issues) encountered during `BrightData.web_data_linkedin_person_profile` calls. Log the error, skip the problematic profile, and continue to the next.
5.  **Store Fetched Data:** Store all successfully fetched profiles in a structured format.
6.  **Iterative Analysis:** Iteratively analyze the extracted, real profiles to identify suitable candidates for all required roles. Continue analysis as more profiles are gathered if initial attempts do not fill all roles.
7.  **Team Assembly:** Assemble the most complete team possible based on real extracted profiles, with justifications for each selection. Clearly note any roles that could not be filled.
8.  **Final Report:** Present a final team report with organizational structure.

## Process Guidelines

-   Use BrightData MCP tools to handle all web interactions.
-   **Primary Data Source:** Prioritize `BrightData.search_engine` for discovering individual employee profiles and `BrightData.web_data_linkedin_person_profile` for extracting detailed data from those profiles.
-   **Error Management:** Implement robust error handling for `BrightData.web_data_linkedin_person_profile` calls, including logging failures and continuing with the process.
-   **Batch Processing:** If a large number of profiles are identified, consider processing them in manageable batches.
-   Implement proper rate limiting and ethical scraping practices.
-   Store all successfully extracted profile data in a structured format for analysis.
-   Apply domain knowledge about construction projects to make informed selections.
-   Provide detailed reasoning for each team member selection.
-   All profile data for analysis MUST be real data extracted directly from LinkedIn via BrightData MCP tools. No mock, dummy, or placeholder profile data should be generated or used for team assembly.
-   If initial profile extraction does not yield suitable candidates for all required roles, the Agent should ensure the search strategy was comprehensive. The goal is to make a best effort to fill all roles with real candidates based on the data obtainable through the specified tools.
-   The `BrightData.web_data_linkedin_company_profile` tool can be used to gather general information about "Gamuda" if needed, but it should not be relied upon as the primary source for a comprehensive list of employee profiles if it only provides a limited sample.

## Required Team Roles

- Project Manager
- Sustainability Specialist
- Architect
- Structural Engineer
- MEP (Mechanical, Electrical, Plumbing) Engineer
- Construction Manager
- Financial Analyst
- Environmental Compliance Officer
- Community Liaison

## Begin the process by:

1.  **Initial Employee Discovery:** Using `BrightData.search_engine` (e.g., Google with a query like `site:linkedin.com/in/ Gamuda employee`), search for LinkedIn profiles associated with "Gamuda".
2.  **Profile Data Extraction:** For each potential profile URL found:
    *   Attempt to extract comprehensive real profile information using `BrightData.web_data_linkedin_person_profile`.
    *   Handle any errors gracefully (log, skip, continue).
    *   Store successfully retrieved profiles.
3.  **Refinement (if needed):** If the initial search provides too many or too few relevant results, refine the search query or consider batch processing.
4.  **Iterative Analysis:** Analyzing the collected real data iteratively.
5.  **Team Assembly:** Assembling and justifying your team selections, striving to fill all roles.

Please execute this entire workflow autonomously, making decisions at each step and providing detailed explanations of your process and reasoning.

This prompt and code will guide RooCode through the complete end-to-end process of team assembly using BrightData MCP to access LinkedIn data. The agent will:

1.  **Discover Employee Profiles:** Use `BrightData.search_engine` to find potential LinkedIn profiles of Gamuda employees.
2.  **Extract Profile Data:** Utilize `BrightData.web_data_linkedin_person_profile` to fetch detailed information for each discovered profile, handling errors appropriately.
3.  **Analyze Profiles:** Analyze the collected real profiles to match skills with required roles.
4.  **Select Team:** Select the best candidates for each position with detailed justifications.
5.  **Report:** Generate a comprehensive team report with organizational structure.

The implementation includes ethical scraping practices, robust error handling, structured data analysis, and detailed reasoning for each selection. The final output will be a markdown report that you can use for your project planning.