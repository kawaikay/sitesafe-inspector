SiteSafe Inspector - Commercial MVP v1

Based on the v42 inspection workflow.

Commercial changes:
1. Independent SiteSafe Inspector product branding.
2. Removed ARUP mark from generated report.
3. Commercial app icon added for 192/512 sizes.
4. Company Branding settings: organisation, team/department, optional company logo.
5. Company branding appears dynamically in generated inspection reports.
6. Offline-first privacy notice added.
7. Existing inspection workflow, saved reports, e-signature, photos, v41 print format and v42 menu-position memory retained.
8. Capacitor-ready package.json and capacitor.config.json added for the next iOS/Android build stage.

Important: this is the commercial PWA/native-ready MVP source. Native iOS/Android project folders are intentionally not bundled because Capacitor dependencies must be installed in a normal Node/Xcode/Android Studio development environment before `npx cap add ios/android`.

Visual in this file was generated with Microsoft Copilot.


Commercial MVP v2 - Flexible Inspection Parties
- Replaced fixed RSS Representative and Contractor Representatives fields with neutral commercial party records.
- Inspection conducted by: name, organisation and selectable role.
- Works inspected / Responsible party: representative name, organisation and selectable role.
- Role lists support Consultant RSS, Main Contractor, Subcontractor, Safety Officer, Site Agent, Engineer, Specialist Contractor, Supplier and Other.
- PDF metadata and e-signature sign-off use the selected inspector identity.
- Older locally saved records remain readable through fallback mapping of previous inspector/contractorRepresentative fields.
