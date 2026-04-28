# Procurement Workflow

A dependency-light procurement workflow website built with Node.js, SQLite, and plain HTML/CSS/JavaScript.

## Run

```powershell
npm.cmd start
```

Then open:

```text
http://localhost:3000
```

## Demo Logins

Requester:

```text
requester@procurement.local
requester123
```

Procurement Admin:

```text
admin@procurement.local
admin123
```

## What It Does

- Starts at a login screen with requester and procurement admin roles.
- Admins can create, edit, delete, and reorder Level 1 activities.
- Each Level 1 can contain any number of Level 2 sub-activities.
- Each Level 2 can contain any number of Level 3 required documents.
- Submitters can only submit a Level 1 when every Level 3 document has a file.
- After a Level 1 is submitted, the entry waits for admin approval.
- Approval moves the entry to the next Level 1 in order.
- Final approval marks the entry complete.
- Uploaded files are stored under `data/documents/<level-1>/<level-2>/<level-3>/`.
- Workflow, entries, approval statuses, and document metadata are stored in `data/procurement.db`.

## Data Location

The default data folder is:

```text
data/
```

For testing or separate environments, set:

```powershell
$env:PROCUREMENT_DATA_DIR = "C:\path\to\data"
npm.cmd start
```
