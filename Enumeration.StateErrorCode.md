---
title: "StateErrorCode"
parent: Enumerations
nav_order: 1
---


# Enumeration: StateErrorCode

Defined in: state/errors.ts:10

Error codes for state management operations.

## Enumeration Members

| Enumeration Member | Value | Description | Defined in |
| ------ | ------ | ------ | ------ |
| <a id="enumeration-member-deserialization_failed"></a> `DESERIALIZATION_FAILED` | `"DESERIALIZATION_FAILED"` | Failed to deserialize string to state | state/errors.ts:15 |
| <a id="enumeration-member-invalid_session_id"></a> `INVALID_SESSION_ID` | `"INVALID_SESSION_ID"` | Session ID format is invalid | state/errors.ts:30 |
| <a id="enumeration-member-invalid_state"></a> `INVALID_STATE` | `"INVALID_STATE"` | Invalid state structure | state/errors.ts:27 |
| <a id="enumeration-member-serialization_failed"></a> `SERIALIZATION_FAILED` | `"SERIALIZATION_FAILED"` | Failed to serialize state to string | state/errors.ts:12 |
| <a id="enumeration-member-session_not_found"></a> `SESSION_NOT_FOUND` | `"SESSION_NOT_FOUND"` | Session not found in storage | state/errors.ts:18 |
| <a id="enumeration-member-storage_error"></a> `STORAGE_ERROR` | `"STORAGE_ERROR"` | Storage operation failed (I/O, permissions, etc.) | state/errors.ts:21 |
| <a id="enumeration-member-version_mismatch"></a> `VERSION_MISMATCH` | `"VERSION_MISMATCH"` | State version mismatch (needs migration) | state/errors.ts:24 |
