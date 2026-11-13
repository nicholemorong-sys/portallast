# ISKOLAR MARSU

A responsive, multi-page scholarship application and monitoring frontend for Marinduque State University. It uses semantic HTML, CSS, and vanilla JavaScript; no frontend framework or package dependencies are required.

## Pages

- `index.html` / `login.html` / `student-login.html`: direct student sign-in
- `admin-login.html`: separate Admin / Staff sign-in
- `register.html`: explains that student accounts are provisioned by an administrator; public self-registration is intentionally disabled
- `student-dashboard.html`: student overview and recent notices
- `admin-dashboard.html`: staff overview, complete applicant register, review actions, student records, scholarship and announcement publishing, and payout schedule management
- `scholarships.html`: searchable scholarship directory and requirements
- `application.html`: scholarship application form and document/image attachments
- `profile.html`: student profile
- `announcements.html`: student announcements
- `tracking.html`: student-only application status and decision view
- `status-tracking.html`: status-tracking destination after an application is submitted
- `payouts.html`: published payout dates and release instructions

Shared assets: `styles.css`, `app.js`, and the local `marsu_logo.png` official logo image.

## Features

- Distinct Student and Admin / Staff entry points. Selecting Admin / Staff leads directly to the separate staff login.
- Student and Admin / Staff sign-in use separate role-specific pages. Entered email and password values create a mock role session for navigation demos on both local and static hosting; public student self-registration remains disabled.
- Student-side scholarship search/filter, application submission, profile editing, announcements, status tracking, and payout viewing.
- Staff-side all-applicant table with search and status/program filters; application detail/document review; approve, reject, and pending actions; CSV export; student account record management; scholarship and announcement publishing; and payout schedule management.
- Application submissions store file names, sizes, and types only in local storage; actual PDF/image data is not saved by this prototype. Admin / Staff can review the metadata in application details. In a real deployment, the actual files must be uploaded to MarSU secure server storage for Admin / Staff review.
- Responsive sidebar navigation, notification panel, keyboard skip link, visible focus states, semantic tables/forms, accessible names, and reduced-motion support.

## Authentication and production integration

This repository is a frontend prototype, not a production scholarship service. Entered email and password values create a mock session for the selected role on local and public static hosting; credentials are not verified and passwords are not stored. Admin / Staff demo access is therefore available to anyone who can open the site and is not secure authentication or authorization. Do not use this prototype to store or manage real applicant information. No authentication API is called by this frontend. Applications, decisions, and other prototype data are stored in the browser's local storage: student submissions and Admin / Staff decisions are shared only when both roles use the same browser profile and site origin, and are not synchronized across different devices or browsers. Application records retain only file metadata; no file bytes are persisted in local storage or IndexedDB. A real deployment must use authenticated MarSU server services for sign-in and role authorization, upload files to secure server storage, and connect application, account, scholarship, announcement, and payout data to the server.

## Run and test

1. Open the folder in VS Code and start Live Server. For a phone on the same Wi-Fi, set the Live Server host to `0.0.0.0`, find the computer's private IPv4 address with `ipconfig`, then open `http://<computer-ip>:8765/` on the phone. Allow the port through the computer firewall on a trusted network if prompted.
2. Verify role routing: Student goes to `student-login.html`; Admin / Staff goes to `admin-login.html`. Use any email and password values to preview the respective dashboards, including on GitHub Pages.
3. Before deployment, connect a test authentication service with separate student/staff test accounts. Confirm a student response cannot enter the staff workspace and an Admin / Staff response cannot enter the student workspace.
4. As a student, test scholarship search/category filtering, required-field validation, multiple PDF/JPG/PNG uploads, profile save, announcement viewing, status tracking, and payout schedules. Confirm status controls are not present in the student UI.
5. As Admin / Staff, test the full applicant list, filtering, application/document view, all three decision actions, CSV export, student record activation, scholarship/announcement publishing, and payout add/edit/remove. Confirm changes are persisted by the authorized service in an integrated deployment.
6. Test keyboard-only use (skip link, navigation, forms, dialog, Escape to close), screen-reader labels/status messages, and layouts at approximately 360px, 768px, and 1280px widths. Check browser console/network errors and verify focus remains visible.

