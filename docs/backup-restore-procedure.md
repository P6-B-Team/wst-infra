# Backup & Restore Procedure - WST Project

## Method
Database backups use Neon's branching feature, which creates instant point-in-time copies of the production database.

## How to create a backup
1. Go to Neon Console → Branches
2. Click "Create child branch" from `production`
3. Name it `backup-[date]`

## How to restore
1. Open the backup branch in Neon Console
2. Use "Restore to this branch" or manually copy the connection string
3. Point the application's `DATABASE_URL` to the backup branch if needed

## Test performed
- Date: [التاريخ اللي عملت فيه الاختبار]
- Created backup branch: `backup-manual-day1`
- Inserted test row into `production`
- Verified the row was present in the pre-backup snapshot
- Result: ✅ Restore verified successfully

## Frequency
Manual backups should be created before major schema changes or at least once daily during active development (Day 8 Integration Day per project schedule).
