# Test Results

**Date:** 2026-02-20  
**Python:** 3.11.4  
**pytest:** 9.0.2  
**Duration:** 1.10s  
**Result:** ✅ 90 passed, 0 failed, 5 warnings  

---

## Summary

| Module | Tests | Passed | Failed |
|--------|-------|--------|--------|
| `test_auth.py` | 13 | 13 | 0 |
| `test_chat.py` | 27 | 27 | 0 |
| `test_graphql.py` | 13 | 13 | 0 |
| `test_health.py` | 9 | 9 | 0 |
| `test_notifications.py` | 14 | 14 | 0 |
| **Total** | **90** | **90** | **0** |

---

## Detailed Results

### test_auth.py — Microsoft SSO Authentication

| # | Test | Status |
|---|------|--------|
| 1 | `TestMicrosoftLogin::test_returns_200_when_sso_configured` | ✅ PASSED |
| 2 | `TestMicrosoftLogin::test_response_contains_authorization_url` | ✅ PASSED |
| 3 | `TestMicrosoftLogin::test_response_contains_state` | ✅ PASSED |
| 4 | `TestMicrosoftLogin::test_returns_500_when_sso_not_configured` | ✅ PASSED |
| 5 | `TestMicrosoftLogin::test_no_auth_required` | ✅ PASSED |
| 6 | `TestMicrosoftCallback::test_successful_callback_returns_200` | ✅ PASSED |
| 7 | `TestMicrosoftCallback::test_callback_response_has_user_hash` | ✅ PASSED |
| 8 | `TestMicrosoftCallback::test_callback_response_has_access_token` | ✅ PASSED |
| 9 | `TestMicrosoftCallback::test_invalid_state_returns_400` | ✅ PASSED |
| 10 | `TestMicrosoftCallback::test_missing_code_returns_422` | ✅ PASSED |
| 11 | `TestMicrosoftCallback::test_missing_state_returns_422` | ✅ PASSED |
| 12 | `TestMicrosoftCallback::test_authorization_failure_returns_401` | ✅ PASSED |
| 13 | `TestMicrosoftCallback::test_multiple_assignments_sets_requires_selection` | ✅ PASSED |

---

### test_chat.py — Chat Endpoints

| # | Test | Status |
|---|------|--------|
| 14 | `TestChatCompletions::test_non_streaming_batch_video_returns_200` | ✅ PASSED |
| 15 | `TestChatCompletions::test_non_streaming_response_structure` | ✅ PASSED |
| 16 | `TestChatCompletions::test_streaming_batch_video_returns_200` | ✅ PASSED |
| 17 | `TestChatCompletions::test_streaming_response_content_type` | ✅ PASSED |
| 18 | `TestChatCompletions::test_streaming_response_ends_with_done` | ✅ PASSED |
| 19 | `TestChatCompletions::test_live_cam_modality` | ✅ PASSED |
| 20 | `TestChatCompletions::test_demo_modality` | ✅ PASSED |
| 21 | `TestChatCompletions::test_chat_model_not_found_returns_404` | ✅ PASSED |
| 22 | `TestChatCompletions::test_batch_video_not_found_returns_404` | ✅ PASSED |
| 23 | `TestChatCompletions::test_live_cam_not_found_returns_404` | ✅ PASSED |
| 24 | `TestChatCompletions::test_demo_video_not_found_returns_404` | ✅ PASSED |
| 25 | `TestChatCompletions::test_no_auth_token_returns_401` | ✅ PASSED |
| 26 | `TestChatCompletions::test_invalid_token_returns_401` | ✅ PASSED |
| 27 | `TestChatCompletions::test_missing_model_hash_returns_422` | ✅ PASSED |
| 28 | `TestChatCompletions::test_missing_message_returns_422` | ✅ PASSED |
| 29 | `TestChatCompletions::test_empty_body_returns_422` | ✅ PASSED |
| 30 | `TestChatCompletions::test_stream_defaults_to_true` | ✅ PASSED |
| 31 | `TestChatCompletions::test_agent_exception_returns_error_event_in_stream` | ✅ PASSED |
| 32 | `TestGetChatHistory::test_returns_empty_history_when_no_thread` | ✅ PASSED |
| 33 | `TestGetChatHistory::test_returns_correct_thread_id_format` | ✅ PASSED |
| 34 | `TestGetChatHistory::test_entity_type_batch` | ✅ PASSED |
| 35 | `TestGetChatHistory::test_entity_type_live` | ✅ PASSED |
| 36 | `TestGetChatHistory::test_entity_type_demo` | ✅ PASSED |
| 37 | `TestGetChatHistory::test_demo_entity_hash_format` | ✅ PASSED |
| 38 | `TestGetChatHistory::test_returns_messages_when_thread_exists` | ✅ PASSED |
| 39 | `TestGetChatHistory::test_no_params_returns_400` | ✅ PASSED |
| 40 | `TestGetChatHistory::test_no_auth_returns_401` | ✅ PASSED |
| 41 | `TestDeleteChatHistory::test_returns_200_on_success` | ✅ PASSED |
| 42 | `TestDeleteChatHistory::test_response_status_is_success` | ✅ PASSED |
| 43 | `TestDeleteChatHistory::test_response_contains_thread_id` | ✅ PASSED |
| 44 | `TestDeleteChatHistory::test_delete_calls_adelete_thread` | ✅ PASSED |
| 45 | `TestDeleteChatHistory::test_delete_with_live_cam` | ✅ PASSED |
| 46 | `TestDeleteChatHistory::test_delete_with_demo_video` | ✅ PASSED |
| 47 | `TestDeleteChatHistory::test_no_params_returns_400` | ✅ PASSED |
| 48 | `TestDeleteChatHistory::test_no_auth_returns_401` | ✅ PASSED |

---

### test_graphql.py — GraphQL Endpoint

| # | Test | Status |
|---|------|--------|
| 49 | `TestGraphQLEndpoint::test_post_returns_200` | ✅ PASSED |
| 50 | `TestGraphQLEndpoint::test_response_is_json` | ✅ PASSED |
| 51 | `TestGraphQLEndpoint::test_typename_query_returns_data` | ✅ PASSED |
| 52 | `TestGraphQLEndpoint::test_invalid_graphql_syntax_returns_error` | ✅ PASSED |
| 53 | `TestGraphQLEndpoint::test_empty_query_returns_error` | ✅ PASSED |
| 54 | `TestGraphQLEndpoint::test_non_json_body_returns_422_or_400` | ✅ PASSED |
| 55 | `TestGraphQLAuthentication::test_request_with_no_auth_still_returns_200` | ✅ PASSED |
| 56 | `TestGraphQLAuthentication::test_request_with_valid_bearer_returns_200` | ✅ PASSED |
| 57 | `TestGraphQLAuthentication::test_request_with_api_key_returns_200` | ✅ PASSED |
| 58 | `TestGraphQLLimits::test_deeply_nested_query_returns_error` | ✅ PASSED |
| 59 | `TestGraphQLLimits::test_introspection_when_disabled` | ✅ PASSED |
| 60 | `TestGraphQLMutations::test_mutation_with_missing_required_args_returns_error` | ✅ PASSED |
| 61 | `TestGraphQLMutations::test_unknown_mutation_returns_error` | ✅ PASSED |
| 62 | `TestGraphQLVariables::test_query_with_variables_accepted` | ✅ PASSED |
| 63 | `TestGraphQLVariables::test_variables_type_mismatch_returns_error` | ✅ PASSED |

---

### test_health.py — Health Check Endpoints

| # | Test | Status |
|---|------|--------|
| 64 | `TestBasicHealthCheck::test_returns_200` | ✅ PASSED |
| 65 | `TestBasicHealthCheck::test_response_contains_status` | ✅ PASSED |
| 66 | `TestBasicHealthCheck::test_response_contains_service_name` | ✅ PASSED |
| 67 | `TestBasicHealthCheck::test_response_contains_version` | ✅ PASSED |
| 68 | `TestBasicHealthCheck::test_no_auth_required` | ✅ PASSED |
| 69 | `TestDetailedHealthCheck::test_returns_200_when_db_healthy` | ✅ PASSED |
| 70 | `TestDetailedHealthCheck::test_response_has_checks_key` | ✅ PASSED |
| 71 | `TestDetailedHealthCheck::test_degraded_when_db_unavailable` | ✅ PASSED |
| 72 | `TestDetailedHealthCheck::test_no_auth_required` | ✅ PASSED |

---

### test_notifications.py — SSE / Notification Endpoints

| # | Test | Status |
|---|------|--------|
| 73 | `TestNotificationsStatus::test_returns_200` | ✅ PASSED |
| 74 | `TestNotificationsStatus::test_response_has_status_key` | ✅ PASSED |
| 75 | `TestNotificationsStatus::test_no_auth_required` | ✅ PASSED |
| 76 | `TestConnectionsCount::test_returns_200` | ✅ PASSED |
| 77 | `TestConnectionsCount::test_response_has_total_connections` | ✅ PASSED |
| 78 | `TestConnectionsCount::test_response_has_connections_by_user` | ✅ PASSED |
| 79 | `TestConnectionsCount::test_zero_connections_when_none_active` | ✅ PASSED |
| 80 | `TestConnectionsCount::test_no_auth_required` | ✅ PASSED |
| 81 | `TestSSEHealth::test_returns_200` | ✅ PASSED |
| 82 | `TestSSEHealth::test_response_status_is_healthy` | ✅ PASSED |
| 83 | `TestSSEHealth::test_response_has_active_connections` | ✅ PASSED |
| 84 | `TestSSEHealth::test_no_auth_required` | ✅ PASSED |
| 85 | `TestSSEStream::test_authenticated_request_returns_200` | ✅ PASSED |
| 86 | `TestSSEStream::test_sse_content_type` | ✅ PASSED |
| 87 | `TestSSEStream::test_connected_event_in_stream` | ✅ PASSED |
| 88 | `TestSSEStream::test_no_auth_returns_401` | ✅ PASSED |
| 89 | `TestSSEStream::test_invalid_token_returns_401` | ✅ PASSED |
| 90 | `TestSSEStream::test_connection_cleanup_called_on_exit` | ✅ PASSED |

---

## Warnings

| # | Warning | Source |
|---|---------|--------|
| 1–2 | `DeprecationWarning`: Passing a class to `strawberry.scalar()` is deprecated. Use `StrawberryConfig.scalar_map` instead. | `models/spectra_ops/audit_trail_tbl.py:7` |
| 3–5 | `RuntimeWarning`: coroutine `AsyncMockMixin._execute_mock_call` was never awaited at `main.py:245` | Triggered in `test_health.py::TestDetailedHealthCheck` |

---

## Issues Fixed During Test Development

### 1. Inline import — `get_observability_callbacks`
Imported inside the `completions()` handler body, not module-level.  
**Fix:** Removed patches; relied on `core.observability` MagicMock stub.

### 2. `verify_access_token` stub behavior
`core.security` replaced with `MagicMock`, causing truthy return for invalid tokens.  
**Fix:** Patched `middleware.auth_middleware.verify_access_token` directly in tests.

### 3. Case-sensitive table name match
`DEMO_TBL` did not match lowercase `"demo"` check.  
**Fix:** Used `str(stmt).lower()` before matching.

---

## How to Run

```bash
# Activate virtual environment
source requirements/venv/Scripts/activate      # Windows (bash)
source requirements/venv/bin/activate          # Linux/macOS

# Run all tests
cd backend
python -m pytest tests/ -v

# Run a single file
python -m pytest tests/test_chat.py -v

# Run a single test
python -m pytest tests/test_chat.py::TestChatCompletions::test_streaming_response_ends_with_done -v

# With coverage
pip install pytest-cov
python -m pytest tests/ --cov=src --cov-report=term-missing
```
