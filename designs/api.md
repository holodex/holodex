# Holodex API design

## User stories

### login

- #32: user can create account
- #26: user can delete their account
- #19: user can login 
- #33: user can log out
 
### groups and members

- #18: user can create a group
  - creating a new group automatically creates an admin and member relationship with the creator
- #36: group admin can invite new members
- group admin can delete their group

### profiles

- #23: user can update their profile
 
### relationships

- #20: user can create personal relationships
  - person can create relationships with self and other agent
- #21: group admin can create group relationships
  - group admin can create relationships with group and other agent
- #24: user can update their personal relationships
- #25: group admin can update group relationships
  - group admin can update relationships with group and other agent
- #29: group admin can delete their group relationships
  - group admin removes relationships with group and other agent.
- #28: user can delete their personal relationships
  - person removes relationships with self and other agent.

### roles

### privacy

- #34: user can control data privacy

## Flows

1. As a new user without an account,
  1. Sign up for an account with email and password
  1. Receive an email with a link containing a signup token
  1. On token success, be logged in
1. As a existing user with an account,
  1. Login to an account with email and password
  1. On credential success, be logged in
1. As a user who wants to create a group,
  1. Create a new group (and become both member and admin of group)
  1. Enter emails of new members
1. As a user invited to group,
  1. Receive an email with a link containing an invite token

## Services

principles:

- token-based authentication (who you are)
- claims-based identity (what you are)
- capability-based authorization (what you may do)

protocols:
- [JSON Web Tokens](http://jwt.io/)
  - [jsonwebtoken]((https://github.com/auth0/node-jsonwebtoken)

### accounts

[accountdown](https://www.npmjs.com/package/accountdown)([-model](https://www.npmjs.com/package/accountdown-model))

- `GET /accounts` to `users.list`
- `GET /accounts/:id` to `users.get`
- `PUT /accounts/:id` to `users.put `
  - TODO what data is associated with an account? ([revelant auth0 docs](https://auth0.com/docs/api/v2#!/Users/patch_users_by_id))

### agents (identities)

### memberships

