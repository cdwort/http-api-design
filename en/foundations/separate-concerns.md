#### Separate Concerns for Direct Users

Heroku's APIs serve two different audiences: customers using the API directly and clients which provide more sophisticated experiences.
Key clients include Dashboard and CLI. 

For our direct API users, we want to keep our APIs clear and easy to understand.
Builders of clients often start out looking like direct API consumers, exploring the API to understand how to build something.

Towards this goal we keep things simple while designing by separating the concerns between the
different parts of the request and response cycle. Keeping simple rules here
allows for greater focus on larger and harder problems.

Requests and responses will be made to address a particular resource or
collection. Use the path to indicate identity, use the body to transfer the
contents and use headers to communicate metadata. Query params may be used as a
means to pass header information also in edge cases, but headers are preferred
as they are more flexible and can convey more diverse information.
