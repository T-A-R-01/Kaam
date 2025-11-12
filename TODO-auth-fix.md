# Authentication Fix Plan

## Issues Identified
- Signup fails because it tries to set localStorage server-side (impossible)
- Login has fallback issues when database is unavailable
- Auth state not persisting after signup redirect

## Files to Edit
- [x] `src/app/signup/actions.ts`: Remove server-side localStorage, return user data
- [x] `src/app/signup/page.tsx`: Handle auth state and redirect client-side
- [ ] `src/app/login/actions.ts`: Ensure proper user data return
- [ ] `src/app/login/page.tsx`: Handle client-side redirect if needed
- [x] `src/lib/auth-new.ts`: Fix login fallback logic

## Testing Steps
- [ ] Test signup with database available
- [ ] Test signup without database (localStorage fallback)
- [ ] Test login with existing users
- [ ] Test login with newly signed up users
- [ ] Verify auth state persists across page reloads
