docs/FEATURES/FEATURE-008.md

Feature: Authentication and Persistent History
Specification Status: APPROVED
Implementation Status: BLOCKED ON CORE-LOOP VALIDATION

Purpose

Introduce user identity immediately before durable cloud-owned practice history becomes necessary.

User Story

As a returning user, I want my practice attempts securely associated with my account so I can access them later.

Scope

Implement:

approved authentication method
account creation/sign-in
secure user identity
persistent cloud attempt storage
user ownership of attempts
row-level security
authenticated history retrieval
migration strategy for eligible local prototype data if justified
sign-out
account deletion requirements

Authentication should not retroactively become required for the anonymous core-loop validation phase unless separately approved.

Out of Scope
social login providers beyond the minimum approved set
teams
organization accounts
public profiles
friends/followers
subscription billing
advanced account personalization
Dependencies
FEATURE-007
core-loop validation
Supabase authentication/data direction
approved persistent data schema
Acceptance Criteria
user can create or access an account through the approved authentication method
authenticated attempt is stored with correct user ownership
user can retrieve their own persistent attempts
user cannot retrieve another user's attempts
row-level security tests prove cross-user access is denied
sign-out removes access to authenticated history
persistent history survives application restart
account deletion removes or schedules deletion of associated user data according to documented policy
authentication is required for persistent cloud history but not unnecessarily coupled to the already-validated anonymous practice architecture