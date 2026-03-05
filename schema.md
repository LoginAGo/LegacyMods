# Supabase Database Schema

This document outlines the planned database schema for LegacyMods.

## Tables

### `profiles`
Extends Supabase's built-in `auth.users`.

| Column | Type | Description |
|--------|------|-------------|
| id | uuid (PK, FK → auth.users) | User ID |
| username | text (unique) | Display name |
| avatar_url | text | Profile picture URL |
| bio | text | Short bio |
| created_at | timestamptz | Account creation date |

---

### `mods`

| Column | Type | Description |
|--------|------|-------------|
| id | uuid (PK) | Mod ID |
| author_id | uuid (FK → profiles) | Uploader |
| name | text | Mod name |
| slug | text (unique) | URL-friendly name |
| description | text | Full description |
| summary | text | Short summary (max 200 chars) |
| tags | text[] | e.g. ['gameplay', 'visual'] |
| file_url | text | Cloudflare R2 file URL |
| file_size | int | File size in bytes |
| downloads | int | Download count |
| status | text | 'active' \| 'removed' \| 'pending' |
| created_at | timestamptz | Upload date |
| updated_at | timestamptz | Last updated |

---

### `mod_versions`

| Column | Type | Description |
|--------|------|-------------|
| id | uuid (PK) | Version ID |
| mod_id | uuid (FK → mods) | Parent mod |
| version_number | text | e.g. '1.0.2' |
| changelog | text | What changed |
| file_url | text | R2 file URL for this version |
| created_at | timestamptz | Release date |

---

### `comments`

| Column | Type | Description |
|--------|------|-------------|
| id | uuid (PK) | Comment ID |
| mod_id | uuid (FK → mods) | Mod being commented on |
| author_id | uuid (FK → profiles) | Commenter |
| body | text | Comment text |
| created_at | timestamptz | Post date |

---

## Row Level Security (RLS)

- Anyone can **read** active mods and comments
- Only authenticated users can **upload** mods or **comment**
- Users can only **edit/delete** their own content
- Admins can update `status` on any mod (for moderation)
