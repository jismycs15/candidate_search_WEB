#candidate_search_web

The React + TypeScript frontend lives in a separate repo/folder (`Frontend/candidate-search`) — see [Running the frontend](#running-the-frontend).
## Prerequisites

| Tool | Version |
| Node.js | A current LTS (20.19+ / 22.12+) — frontend only |

Frontend
- The JWT and refresh token are kept in `localStorage`, so a session survives a reload (the brief allowed local *or* session storage).
- Search-as-you-type is debounced by 450 ms; the Search button runs immediately. Filter state and page are mirrored into the URL query string and restored on load.
- The frontend requests 10 results per page. The brief listed sorting only for the API, so there are no sort controls in the UI.
- A `401` from a protected request triggers one transparent refresh-and-retry; if that fails the stored tokens are cleared and the user is sent to the login screen.
