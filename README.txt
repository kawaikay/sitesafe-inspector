Site Safety Inspection PWA v4

Added databanks:
- Foundation & Piling Works: FP1-FP20
- Excavation & Lateral Support (ELS): EL1-EL20

The additions consolidate recurring observations from the supplied CHR weekly safety reports (March-August 2023), including plant stability and visibility, piling pins and guards, casings/drilling-rod wedging, lifting points and gear, Form 4, permit-to-dig, slope stability/protection, guardrails, access, openings, water control, temporary services and public protection.

PDF enhancement:
- Every FAIL item is summarized under General Safety Issues Identified.
- Only selected PASS/FAIL/N/A items are shown.
- Photos remain offline, include a permanent timestamp overlay, and appear under the selected item.

Deployment:
Upload all extracted files to the existing GitHub repository root and replace files with the same names. GitHub Pages will redeploy automatically. The service-worker cache is v4.

DATABANK EXTENSION v5
Included additional Weekly Safety Inspection Reports dated 9 Aug 2023 to 6 Nov 2023.
New items FP21-FP30, EL21-EL27, D5-D6, R4 and W6 cover load indicators/alarms, lifting fatal zones, hook and latch condition, SWL identification, wire-sling storage, mixed-load lifting, plant isolation, hose integrity, operator refresher training, scaffold/access inspection, toe boards, checking-point covers, stagnant water, haul-road routing, securely fixed barriers, sump-pit lifesaving equipment, lifting/scaffold documentation, adverse weather and unattended flame cutting.

DATABANK ORGANISATION v6
- Foundation & Piling Works and Excavation & Lateral Support (ELS) are no longer separate Main Categories.
- All additional controls derived from the supplied CHR WSI reports have been allocated into the existing Main Categories: Lifting Operations, Piling Operations, PPE, Documentation, Excavation & Slope, Access & Egress, Falling Objects Protection, Housekeeping, Electrical Safety and Site Rules.
- Existing category names and mobile navigation are retained.


DATABANK CONSOLIDATION v7
Semantically overlapping items were merged while preserving the more complete control wording. Separate controls were retained where inspection evidence differs, such as extinguisher location versus certification, or access versus edge protection.

GENERAL HYGIENE CONDITION v8
Added General Hygiene Condition / 一般衛生情況 as a Main Category with GH1-GH12 covering cleanliness, waste, food waste, mosquito breeding, pest control, toilets/washing facilities, hand washing, drinking water, welfare areas, drainage and dust/mud hygiene.
FAIL items automatically feed the existing General Safety Issues Identified section using hygiene risk groups such as Cleanliness, Waste, Pest Control, Sanitary Facilities, Drinking Water, Welfare Facilities, Drainage and Dust/Mud.


ARUP PAGE MARK v9
- Added a red ARUP text mark at the top-right of every printed PDF page.
- The implementation uses a fixed print element so the browser print engine repeats it on each A4 page.
- This is a text reproduction matching the supplied visual reference, not an embedded official logo asset.


PHOTO DELETE FUNCTION v10
- Each stored photo thumbnail now has a red X delete button.
- The user is asked to confirm before deletion.
- Deletion removes the photo from IndexedDB, so the removed photo will not appear in the offline PDF.
- Users can immediately retake a clearer photo using Take Photo.


v11 REPORT / PHOTO OPTIMISATION
- Changed Inspector label to RSS Representative / 駐地工程師代表 in the PWA input form.
- Changed PDF report field from Inspector to RSS Representative.
- Reduced stored photo long edge from 1800 px to 1280 px.
- Reduced JPEG quality from 88% to 70% to reduce IndexedDB storage and PDF file size while retaining sufficient visual detail for normal safety observations.
- Timestamp, inspection number and item number remain burned into each stored image.


v12 PHOTO REPORT LAYOUT
- Removed the separate large Photo Taken date/time caption below photos in the PDF report.
- Date/time remains permanently burned into the lower part of each stored photo, together with Item ID and Inspection ID.
- The small date/time beneath the thumbnail inside the PWA remains available for checking before report export.

v13 PHOTO THUMBNAIL TIMESTAMP
- Increased the timestamp displayed below each photo thumbnail in the PWA inspection screen to 14 px, bold, dark text.
- Added 6 px spacing above the timestamp for readability on mobile phones.
- PDF layout is unchanged: the separate large timestamp below PDF photos remains removed because date/time is already burned into each photo.


v14 REPORT HEADER
- Moved the red ARUP mark into the right-hand side of the formal report header zone.
- Changed Inspection to Inspection Report Ref. No.
- Existing offline, timestamped photo, RSS Representative, hygiene, deduplication, compression and photo-delete functions remain.


v15 MANUAL INSPECTION REPORT REFERENCE
- Inspection Report Ref. No. is now a manual input field on the main inspection form.
- The manually entered reference is saved with the offline report and shown in the PDF.
- The internal generated ID remains hidden and is retained only for IndexedDB/photo linkage.
- New photos use the manual report reference in the burned-in stamp when one has been entered.


v16 PDF FILE NAME
- Before opening the browser print/PDF dialog, the document title is temporarily changed to the manually entered Inspection Report Ref. No.
- Safari/Chrome normally use this title as the suggested PDF filename.
- Invalid filename characters \ / : * ? " < > | are replaced with hyphens.
- The visible report reference and the suggested PDF filename therefore match.
- The original PWA title is restored after printing.


v17 SAVED REPORT MANAGEMENT
- Saved Reports now display the manually entered Inspection Report Ref. No. as the primary report name.
- Older reports without reportRef fall back to Project, then internal ID.
- Added Delete / 刪除 button beside Open.
- Deleting a saved report asks for confirmation and removes both the saved report record and all photos linked to that report from IndexedDB.


v18 MOBILE SCROLL POSITION FIX
- PASS/FAIL/N/A selection now updates only the selected item card and no longer rebuilds the category list, so selecting F7 does not jump back to F1.
- Taking a photo may still require a category refresh to show the new thumbnail, but the exact vertical scroll position is saved and restored after the refresh.
- Deleting a photo also preserves the current vertical position.


v19 MAIN CATEGORY RETURN-POSITION FIX
- When Finish Category is pressed, the app returns to the Main Categories screen at the same category card just completed instead of returning to the first category.
- Example: complete General Hygiene near the bottom, press Finish Category, and General Hygiene remains centred on screen.
- The Back button from a category follows the same behavior.
- Opening the PWA normally still starts at the top of Main Categories.


v20 SUB-ITEM DRILL-DOWN NAVIGATION
- Opening a Main Category now shows a compact list of all sub-items first.
- Each sub-item displays its current state: OPEN, PASS, FAIL or N/A.
- Tapping a sub-item opens a dedicated detail page for PASS/FAIL/N/A, remarks and photo capture.
- Detail page includes Previous, Item List and Next navigation.
- Returning to the item list does not lose status, remarks or photos.
- Finish Category remains on the sub-item list and returns to the same Main Category position.

v21 PPE EXPANSION
Added five PPE controls for correct safety-helmet use/condition and working-at-height fall protection using full-body safety harness, secure anchorage/lifeline and pre-use equipment checks.

v22 PPE GENERAL COMPLIANCE
Added a general PPE compliance item covering safety helmet, safety footwear, high-visibility vest, and safety harness where applicable.

v23 DOCUMENTATION DEDUPLICATION
- Removed duplicated scaffold documentation item D6 because D2 already covers valid Form 5/equivalent and competent-person inspection for newly erected metal scaffolding.
- Remaining Documentation items were renumbered sequentially to avoid an ID gap.

v24 CONFINED SPACE REVISION
Confined Space checklist revised to C1-C17 based on the supplied Hong Kong Labour Department confined-space regulation summary. It now covers competent-person risk assessment, certificate/permit, isolation, atmospheric testing, cleaning/ventilation, ingress prevention, certified workers, standby communication, continuous precautions, respiratory equipment, harness/lifeline, emergency procedures/equipment, trained rescue personnel and worker instruction/training.

v25 HONG KONG CONSTRUCTION-SITE TOTAL SMOKING BAN
Updated smoking-related checks for the construction-site-wide smoking prohibition effective 17 July 2026. Legacy narrow controls such as no smoking only during plant operation were removed/superseded. Site Rules now cover total site prohibition, lighting/smoking/carrying lit smoking products, contractor/subcontractor reasonable steps, removal of smoking points/ashtrays, and communication/enforcement for workers/visitors/delivery personnel. Fire Safety includes a check for cigarette butts/evidence of smoking as a fire-risk indicator.

v26 LIFTING CASEBOOK CASE 1 & CASE 6
Added Lifting Operations checks based on Labour Department Lifting Operation Accident Casebook:
- Case 1: pre-use/periodic hook and safety-latch condition and functionality.
- Case 6: truck-mounted crane outriggers fully extended; appropriate pads/blocks with bearing area at least three times the outrigger float area unless otherwise specified by manufacturer; pads suitable for slopes; and suitable crane/setup location with adequate space and acceptable ground level/slope.

v27 PRACTICAL CONFINED SPACE CHECKLIST
Reduced the Confined Space checklist from 17 regulatory-detail items to 12 practical site-inspection items focused on new-build pipeline, chamber and water-tank construction. The revised controls cover risk assessment/permit, isolation, atmospheric testing, forced ventilation, flooding/material ingress, safe access and lighting, certified entrants, standby communication and entry records, continuous monitoring, rescue readiness, and guarding against unauthorized entry.

v28 SITE RULES UPDATE
- Removed Site Rules items R11 and R12 as requested.

v29 ELECTRICAL SAFETY E3
Replaced E3 with: Suitable waterproof socket is provided and used for electric arc welding equipment. / 電弧焊設備已提供並使用合適的防水插座。


v30 CONTRACTOR REPRESENTATIVES AND E-SIGNATURE
- Added Contractor Representatives / 承建商代表 below RSS Representative in the form and report particulars.
- Added finger/stylus e-signature dialog with Clear, Save and Delete functions.
- Signature is stored locally with that report and restored when reopened.
- Added PDF sign-off block with Report prepared by, RSS Representative, Date of report and Signed. No contractor signature box is included.


v31 OTHERS CATEGORY
- Added Others / 其他 as a Main Category for safety issues not covered by the prescribed checklist.
- OT1: Other safety issue not covered by the prescribed inspection items / 其他未涵蓋於既定檢查項目的安全問題.
- The existing detail workflow allows PASS/FAIL/N/A, free-text Remarks, photo capture, photo deletion and timestamping. For an actual unlisted issue, use OT1 with FAIL, describe the issue in Remarks, and attach supporting photo(s).
- OT1 appears in the selected-items-only PDF and feeds General Safety Issues Identified when marked FAIL.


v32 OTHERS EXPANSION
Expanded Others / 其他 from OT1 to OT1-OT10 so users can quickly classify uncatalogued safety observations before adding remarks and photos.


v33 CANTONESE VOICE REMARKS
- Added a microphone button beside Remarks on each sub-item detail page.
- SpeechRecognition language is set to zh-HK for Cantonese/Hong Kong Chinese recognition.
- Recognized speech is appended to the existing remark rather than replacing it.
- Microphone permission is required. Browser support varies; some browsers use a server-based recognizer and therefore voice recognition may require an internet connection even though the rest of the PWA works offline.


v34 BILINGUAL VOICE REMARKS
- Added separate Cantonese and English speech-input buttons beside Remarks.
- Cantonese uses zh-HK. English uses en-HK.
- Recognized speech is appended to existing remarks.


v35 TRILINGUAL VOICE REMARKS
- Added Mandarin / 普通話 speech input using zh-CN.
- Remarks now support Cantonese (zh-HK), Mandarin (zh-CN) and English (en-HK).
- Recognized speech is appended to existing remarks.


v36 REMARK PLACEHOLDER
Changed the Remarks placeholder to: Enter remarks or use voice input / 輸入備註或使用語音輸入, matching Cantonese, Mandarin and English voice input.


v37 NATIVE KEYBOARD DICTATION
- Removed the three in-app Web Speech language buttons because browser speech recognition was unreliable on the tested iPhone/PWA.
- Remarks now instruct the user to tap the Remarks field and use the native phone keyboard microphone/dictation.
- Native keyboard dictation can be used with Cantonese, Mandarin or English according to the keyboards/dictation languages configured on the phone.
- This avoids the former Speech recognition unavailable message.


v39 PROFESSIONAL REPORT REDESIGN
Redesigned report hierarchy, metadata table, typography, category bars, observation boxes, photo/remarks grid, summary cards, issues list and sign-off for a formal A4 RSS inspection report.


v41 COMPACT TWO-ITEM PRINT LAYOUT
- Reduced A4 margins, report metadata height, category spacing, item heading size, photo cell height and remarks typography so a normal report page can accommodate at least two typical inspection observation blocks.
- Category heading remains attached to its first observation.
- Observation blocks still avoid splitting across pages.
- Exception: an unusually tall item with many photos or long remarks may require more than half a page.


v42 MENU POSITION MEMORY
- Main menu now remembers the exact scroll position/category before entering a category and restores it on Back or Finish Category.
- Sub-item menu now remembers the exact scroll position/sub-item before opening an item and restores it on Item List or the top Back button.
- The selected item is used as a fallback anchor if the exact scroll position cannot be restored.
- Position memory is stored in sessionStorage so it survives screen rerenders within the current PWA session without changing inspection data.
