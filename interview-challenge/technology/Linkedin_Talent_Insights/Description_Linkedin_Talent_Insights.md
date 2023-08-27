# Business Problem Statement:
In the ever-evolving talent landscape, keeping track of the data-driven insights related to professionals, skills, migration patterns, and industry trends is imperative for LinkedIn's "Talent Insights" team. We want to ensure that our recruiters and partnering companies are equipped with the best intelligence tools to make informed decisions. The challenge for our data scientist would be to gain insights from our extensive database of professionals, decipher patterns, and drive intelligent solutions.

## Data Tables:

**`TalentProfiles`:**

| Column Name | Description | Feature Type |
|:-----------:|:-----------:|:------------:|
| `ProfileID` | Unique ID for each profile | Categorical |
| `Skill` | Primary Skill of the Professional | Categorical |
| `Experience` | Years of experience | Numerical |
| `Industry` | Industry they belong to | Categorical |
| `CurrentLocation` | Current city of the professional | Categorical |
| `PastLocation` | Previous city of the professional | Categorical |
| `Role` | Job role of the professional | Categorical |

**`IndustryTrends`:**

| Column Name | Description | Feature Type |
|:-----------:|:-----------:|:------------:|
| `Industry` | Name of the industry | Categorical |
| `TrendRating` | Trendiness rating (1-10) | Numerical |
| `Demand` | Number of job postings | Numerical |

**`SkillMigration`:**

| Column Name | Description | Feature Type |
|:-----------:|:-----------:|:------------:|
| `Skill` | Name of the skill | Categorical |
| `MigrationCount` | Number of professionals who shifted to another skill | Numerical |
| `NewSkill` | The skill they shifted to | Categorical |

## Questions:

1. **Scenario**: Given that there's been a buzz around a specific emerging industry, we'd like to see how it influences professionals in our network.
   - **Question**: Can you identify the top 3 roles within the emerging industry that has the highest trend rating from the `IndustryTrends` table? How do these roles compare in terms of experience and migration patterns from the `TalentProfiles` and `SkillMigration` tables?


2. **Scenario**: We've noticed some skills are becoming obsolete while others are gaining traction.
   - **Question**: Using the `SkillMigration` table, can you determine which top 3 skills are witnessing the highest migration? To which new skills are professionals mostly transitioning?


3. **Scenario**: We're interested in identifying a city that could potentially be the next big hub for an industry showing rapid growth.
   - **Question**: Based on the `TalentProfiles` table, can you determine which city has the maximum influx (difference between current and past location) of professionals belonging to the industry with the highest trend rating? What are the predominant skills of these professionals?


4. **Scenario**: We are planning to introduce a recommendation algorithm for "people you may know" within specific industries.
   - **Question**: Using the `TalentProfiles` table, create a machine learning model that predicts the `Industry` based on a professional's `Skill`, `Experience`, and `Role`. Clearly mark `Industry` as the target variable.
