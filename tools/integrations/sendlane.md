# Sendlane

Unified email, SMS, and reviews platform for ecommerce.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST v2 |
| MCP | - | Not available |
| CLI | - | Not available |
| SDK | - | HTTP only |

## Authentication

- **Type**: Bearer token
- **Header**: `Authorization: Bearer {token}`

## Agent Notes

- Unifies email, SMS, and reviews in one platform, which removes the coordination problem of running review requests from a separate system than the lifecycle flows.
- Same evaluation applies as any ESP: check flow coverage against the twelve in `lifecycle-flows` before optimizing content.
- Review request timing should trigger on **delivery plus a use-period delay**, not on order date. Verify how the platform is configured.
- **Related skills**: `lifecycle-flows`, `email-sms-campaigns`, `reviews-and-reputation`
