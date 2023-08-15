# **Business Problem Statement:**  

The Google Knowledge Graph team is aiming to expand the knowledge base with new entries and relationships. We have gathered a large dataset of web page metadata and user interaction data. The goal is to identify relevant entries, understand the relationships between these entities, and predict possible connections that would be of interest to users. By doing so, we can improve the richness and context-awareness of search results.

## **Data Tables:**

1. **WebPageData**

| Column Name      | Description                                               | Feature Type          |
   |------------------|-----------------------------------------------------------|-----------------------|
   | page_id          | Unique Identifier for the webpage                         | Categorical (Nominal) |
   | content_text     | Extracted textual content from the webpage                | Text                  |
   | page_link        | Hyperlink URL                                             | Text                  |
   | associated_tags  | Tags or keywords related to the webpage                  | List of Text          |

2. **UserInteractions**

| Column Name   | Description                                               | Feature Type          |
  |---------------|-----------------------------------------------------------|-----------------------|
   | user_id       | Unique Identifier for the user                            | Categorical (Nominal) |
   | page_id       | Unique Identifier for the webpage                         | Categorical (Nominal) |
   | action_type   | Type of action (click, dismiss, ignore)                   | Categorical (Nominal) |
   | timestamp     | When the user interaction occurred                        | DateTime              |

3. **EntityRelationships**

| Column Name   | Description                                               | Feature Type          |
   |---------------|-----------------------------------------------------------|-----------------------|
   | entity_1      | First entity in the relationship                          | Text                  |
   | entity_2      | Second entity in the relationship                         | Text                  |
   | relationship  | Type of relationship (e.g., "is a type of", "is located in")| Categorical (Nominal) |



## **Questions:**

1. **Entity Recognition in Web Content**  
    Imagine there are billions of web pages and the Google Knowledge Graph has millions of entities already. You need to expand it further. Given the `WebPageData` table, use text analysis techniques to extract potential entities from the `content_text` column which aren't already in the Knowledge Graph.  

2. **User Interaction Analysis**  
    Using the `UserInteractions` table, for each action type (click, dismiss, ignore), find the pages with the highest interaction count. Next, among these pages, identify those that are skewed towards more dismiss actions. This will help in understanding which potential knowledge graph entities might not be of interest to users.   

3. **Identifying Relationships**  
    After extracting entities from web pages, you need to identify relationships between them. Using the `EntityRelationships` table, suggest a method to predict new relationships between entities based on existing ones. How would you evaluate the performance of this relationship prediction?   

4. **A/B Testing on Relationships**  
    Suppose you added a new set of entities and relationships to the Google Knowledge Graph. To ensure its efficacy, you decided to conduct an A/B test where some users are exposed to the new expanded graph (version B) while others to the original (version A). Using the `UserInteractions` table, how would you assess if the new relationships in version B lead to better user engagement?  
