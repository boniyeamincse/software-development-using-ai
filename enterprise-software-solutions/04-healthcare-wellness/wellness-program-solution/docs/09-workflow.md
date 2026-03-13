# 09 - Wellness System Workflows

## The Onboarding & HRA Journey
1. **Enrollment**: Employee downloads the app via corporate SSO (Okta/AD).
2. **Device Sync**: User connects Apple Health/Fitbit; System performs historical ingest.
3. **Assessment**: User completes the 5-minute Health Risk Assessment.
4. **Scoring**: AI engine calculates health score and identifies "Stress" as a focus.
5. **Onboarding**: User is automatically invited to a "30-Day Mindfulness Challenge."
6. **Points**: User earns 500 points for completing the setup.

## The Challenge & Rank Workflow
1. HR launches a "Global Walking Challenge" (2-weeks).
2. Users join; Activity data flows in real-time.
3. System calculates daily "Bonus Points" for consistency.
4. Leaderboard updates every 5 minutes using Redis caching.
5. Challenge ends; Top 10% receive "Gold Badges" and insurance credit.
6. Summary report added to the HR dashboard.

## The Incentive Fulfillment Workflow
1. User reaches "Premium Tier" status (accumulated 5,000 points).
2. User selects "Health Insurance Discount" in the Reward Shop.
3. System generates an API trigger to the Insurance/Payroll platform.
4. Confirmation sent to the user; HR dashboard reflects the corporate saving.
5. Transaction finalized in the immutable audit vault.

---
[← Previous: UI Pages](08-ui-pages.md) | [Back to Index](README.md) | [Next: Technology Stack →](10-tech-stack.md)
