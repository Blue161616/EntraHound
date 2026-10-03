# Security policy

EntraHound is a read-only assessment tool that runs entirely in the browser. It
never writes to a tenant and never sends tenant data anywhere but Microsoft
Graph.

## Reporting a vulnerability

If you find a way EntraHound could leak tenant data, write to a tenant, execute
code from collected data, or mislead an assessor (for example a missing edge
that is reported as "does not exist" rather than "not collected"), please report
it privately to **derk@blue16.nl** rather than opening a public issue. You will
get an acknowledgement within three working days.

## Scope notes

- The page loads two third-party libraries (MSAL, Cytoscape) with Subresource
  Integrity pinned. Bumping either version requires recomputing the hash.
- Everything the tool displays is escaped before it reaches the DOM; tenant
  object names are untrusted input.
- An access token pasted in "external token" mode stays in the tab's memory and
  is never stored.
