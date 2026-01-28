# Zoom Meeting Assistant

## Problem Statement

Transcribe and summarize meetings.
[Question Description](https://medium.com/@godwintrav/how-i-designed-a-real-time-meeting-assistant-like-otter-ai-fireflies-ai-system-design-breakdown-823027e560de)

### Requirements

- Record and Transcibe Meetings.
- Generate Highlights after meetings.
- Send users the summary when ready.

- Scability, Availability, Low-latency, Easy to monitor and alert

### Approach

### Design

**Data Model with ID Relationships:**

**User Table** (stores participants)

- `user_id` (PK) - Unique identifier for each user
- `email` - User email
- `name` - User name

**Meeting Table** (stores meeting metadata)

- `meeting_id` (PK) - Unique identifier for each meeting
- `title` - Meeting title
- `start_time` - When meeting started
- `end_time` - When meeting ended
- `created_at` - When record was created

**UserMeeting Table** (junction table: many-to-many relationship)

- `id` (PK) - Record identifier
- `user_id` (FK → User) - Links to user who participated
- `meeting_id` (FK → Meeting) - Links to meeting
- `joined_at` - When user joined

**Transcription Table** (stores raw transcribed text)

- `transcription_id` (PK) - Unique identifier
- `meeting_id` (FK → Meeting) - Which meeting this belongs to
- `speaker_user_id` (FK → User) - Which user was speaking
- `timestamp` - When in the meeting was this spoken
- `transcribed_text` - The actual text

**Summary Table** (stores generated summaries)

- `summary_id` (PK) - Unique identifier
- `meeting_id` (FK → Meeting) - Which meeting this summarizes
- `generated_at` - When summary was generated
- `summary_text` - The actual summary
- `highlights` - Key points from the meeting

## API and Web Event Design

I use WebSocket not RestAPI design because the application is real-time not request-response based.

**AuthService**
POST /register/user
POST /register/login

**MeetingService**
GET /meeting/summary
POST /meeting/started

### Scalability

[Discuss how the system can be scaled to handle increased load]

### Performance

[Consider the performance characteristics of the system]

### Trade-offs

[Discuss any trade-offs made during the design process]

### Next Steps

[Outline any next steps or follow-up actions]

### Example Usage

[Provide an example usage scenario for the system]

### References

[List any relevant resources or references]

### Design

[Provide a high-level design of the system]

### Scalability

[Discuss how the system can be scaled to handle increased load]

### Performance

[Consider the performance characteristics of the system]

### Trade-offs

[Discuss any trade-offs made during the design process]

### Next Steps

[Outline any next steps or follow-up actions]

### Example Usage

[Provide an example usage scenario for the system]

### References

[List any relevant resources or references]
