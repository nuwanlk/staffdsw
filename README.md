# Staff Management System

A modern, dark-themed web application for managing staff members with Supabase backend.

## Features

- **Dashboard**: Real-time statistics and analytics
  - Total staff count
  - Gender distribution
  - Monthly additions
  - Charts by designation and grade
  - Recent activity feed

- **Add Staff**: Comprehensive form for staff registration
  - Personal information
  - Contact details
  - Employment history
  - Education qualifications
  - Family information (spouse & children)
  - Efficiency bar exams
  - Promotions
  - Leave information

- **Search Staff**: Advanced search and filtering
  - Search by name, designation, grade, gender, NIC, marital status
  - Expandable detailed view
  - CSV export functionality

## Setup Instructions

### 1. Supabase Setup

1. Create a Supabase account at https://supabase.com
2. Create a new project
3. Go to the SQL Editor and run the following SQL to create the table:

```sql
create table public.staff_members (
  id uuid not null default gen_random_uuid (),
  name_with_initials text null,
  name_full_sinhala text null,
  name_full_english text null,
  designation text null,
  grade text null,
  gender text null,
  nic_number text null,
  phone_no text null,
  whatsapp_no text null,
  email_address text null,
  permanent_address text null,
  marital_status text null,
  first_appointment_date date null,
  previous_appointment_designation text null,
  previous_appointment_date date null,
  is_appointment_permanent boolean null,
  permanent_date date null,
  education_qualifications text null,
  efficiency_bar_exam_grade3_date date null,
  efficiency_bar_exam_grade2_date date null,
  efficiency_bar_exam_grade1_date date null,
  promoted_to_grade2_date date null,
  promoted_to_grade1_date date null,
  promoted_to_special_grade_date date null,
  promoted_to_supra_date date null,
  leave_from_date date null,
  leave_to_date date null,
  transferred_to_current_institute_date date null,
  spouse_name text null,
  spouse_designation text null,
  spouse_workplace text null,
  children jsonb null,
  has_disability text null,
  pension_date date null,
  resignation_date date null,
  moved_to_another_service_date date null,
  dismissal_date date null,
  created_at timestamp with time zone null default now(),
  constraint staff_members_pkey primary key (id)
) TABLESPACE pg_default;
```

4. Get your Supabase credentials:
   - Go to Project Settings → API
   - Copy the `Project URL` (SUPABASE_URL)
   - Copy the `anon public` key (SUPABASE_ANON_KEY)

### 2. Configure the Application

Open each HTML file (index.html, insert.html, search.html) and replace the following lines:

```javascript
const SUPABASE_URL = 'YOUR_SUPABASE_URL';
const SUPABASE_ANON_KEY = 'YOUR_SUPABASE_ANON_KEY';
```

With your actual Supabase credentials:

```javascript
const SUPABASE_URL = 'https://your-project.supabase.co';
const SUPABASE_ANON_KEY = 'your-anon-key-here';
```

### 3. Run the Application

Simply open `index.html` in a web browser. No server required!

The application uses:
- Supabase for backend/database
- Pure HTML/CSS/JavaScript (no build process needed)
- CDN-loaded Supabase client library

## File Structure

```
├── index.html      # Dashboard page
├── insert.html     # Add staff form
├── search.html     # Search and filter page
└── README.md       # This file
```

## Design Features

- Dark theme with accent colors
- Animated transitions and micro-interactions
- Responsive grid layouts
- Custom form styling
- Real-time data updates
- Export to CSV functionality

## Browser Support

Works on all modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari

## Security Notes

- The `anon` key is safe to use in client-side code
- For production, consider implementing Row Level Security (RLS) in Supabase
- Add authentication if needed for user-specific access

## Troubleshooting

**Can't connect to Supabase:**
- Check that your SUPABASE_URL and SUPABASE_ANON_KEY are correct
- Ensure the table is created in your Supabase project
- Check browser console for errors

**Data not displaying:**
- Verify the table has data
- Check browser console for JavaScript errors
- Ensure you're using a modern browser

**Form submission fails:**
- Check Supabase credentials
- Verify network connection
- Look for validation errors in the form

## License

This is a custom application. Modify as needed for your organization.
