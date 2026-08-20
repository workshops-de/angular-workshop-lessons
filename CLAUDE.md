# Lessons

This repository only contains lessons for the Angular Workshop.
To understand how to structure lessons, in order to create and update them correctly, refer to [lessons.md](./docs/lessons.md).

# Slides

Currently, no slidev slides are planned in this repository.
Slides live at Google Slides.
Topics are spread among different presentations.

## Google Slides - Presentation IDs

| Präsentation    | ID                                             |
| --------------- | ---------------------------------------------- |
| Angular Basics  | `1KJMDvEUIWDHluMPLffiBnadVSO2IElTAs7jPsMadehw` |
| Angular Routing | `193jtyGRGHGKr7gwHP-jWj8IcENWggzpPClVxmFgPAkY` |
| Angular Testing | `1zRNyaH3lcOhChTl4VIetlSV8WScYLzxvzZ3Mx8zp8xA` |
| Angular Forms   | `1Ue8_s_nz09Yc0RT2I38fmE5hlbF8oz_quzSRODPX_ZA` |

## Google Slides MCP

### Available Tools

- **`create_presentation`**: Creates a new Google Slides presentation.
  - **Input:**
    - `title` (string, required): The title for the new presentation.
  - **Output:** JSON object representing the created presentation details.

- **`get_presentation`**: Retrieves details about an existing presentation.
  - **Input:**
    - `presentationId` (string, required): The ID of the presentation to retrieve.
    - `fields` (string, optional): A field mask (e.g., "slides,pageSize") to limit the returned data.
  - **Output:** JSON object representing the presentation details.

- **`batch_update_presentation`**: Applies a series of updates to a presentation. This is the primary method for modifying slides (adding text, shapes, images, creating slides, etc.).
  - **Input:**
    - `presentationId` (string, required): The ID of the presentation to update.
    - `requests` (array, required): An array of request objects defining the updates. Refer to the [Google Slides API `batchUpdate` documentation](https://developers.google.com/slides/api/reference/rest/v1/presentations/batchUpdate#requestbody) for the structure of individual requests.
    - `writeControl` (object, optional): Controls write request execution (e.g., using revision IDs).
  - **Output:** JSON object representing the result of the batch update.

- **`get_page`**: Retrieves details about a specific page (slide) within a presentation.
  - **Input:**
    - `presentationId` (string, required): The ID of the presentation to retrieve.
    - `pageObjectId` (string, required): The object ID of the page (slide) to retrieve.
  - **Output:** JSON object representing the page details.

- **`summarize_presentation`**: Extracts and formats all text content from a presentation for easier summarization.
  - **Input:**
    - `presentationId` (string, required): The ID of the presentation to summarize.
    - `include_notes` (boolean, optional): Whether to include speaker notes in the summary. Defaults to false.
  - **Output:** JSON object containing:
    - `title`: The presentation's title
    - `slideCount`: Total number of slides
    - `lastModified`: Revision information
    - `slides`: Array of slide objects containing:
      - `slideNumber`: Position in presentation
      - `slideId`: Object ID of the slide
      - `content`: All text extracted from the slide
      - `notes`: Speaker notes (if requested and available)
