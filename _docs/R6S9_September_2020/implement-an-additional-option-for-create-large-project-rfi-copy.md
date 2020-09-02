---
title: '46512'
category: R6S9
order: 1
---

> **Implement an additional option for 'Create Large Project RFI' in the options dropdown on the top right hand corner of the Project Details page in the Grants Manager.**
>
>
>
> * Note: This does not apply to Management Costs.
> * ***IF \[THE PROJECT HAS AN ASSOCIATED STREAMLINED PROJECT APPLICATION\] AND \[PROJECT IS A LARGE PROJECT BASED ON THE BEST AVAILABLE COST (NOT 104 COST TYPE)\] AND (\[THERE IS A LARGE PROJECT SURVEY/SCHEDULE AND THERE IS ALSO A PENDING OR COMPLETED LARGE PROJECT RFI\] OR \[*THERE IS NOT A LARGE PROJECT SURVEY/SCHEDULE\])**\*\*
>   * Beneath the first horizontal rule (just above the existing Create RFI button) in the options dropdown, display an additional option for '\[fas fa-plus\] Create Large Project RFI'
>     * *IF&nbsp;*THERE IS A LARGE PROJECT SURVEY/SCHEDULE AND THERE IS ALSO A&nbsp;*COMPLETED*&nbsp;LARGE PROJECT RFI\*\*
>       * Disable this option and display a bootstrap popover message that reads:
>         * HEADER
>           * Disabled
>         * MAIN TEXT
>           * A large project RFI cannot be created for this project because it already has a Large Project \[Schedule/Survey\] form associated with it.
>     * **IF&nbsp;*THERE IS A LARGE PROJECT SURVEY/SCHEDULE AND THERE IS ALSO A PENDING LARGE PROJECT RFI***
>       * Disable this option and display a bootstrap popover message that reads:
>         * HEADER
>           * Disabled
>         * MAIN TEXT
>           * A large project RFI cannot be created for this project because it's already pending Large Project RFI.
>     * Permissions for this button are:
>       * System Admin
>       * FEMA Admin
>       * *IF PENDING CRC PROJECT DEVELOPMENT*
>         * This should match the existing permissions for the Create RFI Button for this step.
>       * *IF PENDING PEER REVIEW*
>         * This should match the existing permissions for the Create RFI Button for this step.
>       * *IF PEDNING FEMA 406 HMP COMPLETION*
>         * This should match the existing permissions for the Create RFI Button for this step.
>       * *IF PENDING INSURANCE COMPLETION*
>         * This should match the existing permissions for the Create RFI Button for this step.
>     * Clicking this button should open up a modal that reads:
>       * HEADER
>         * Create Large Project Request for Information
>       * BODY
>         * At the top of the modal, display a yellow alert that reads:
>           * ICON
>             * fas fa-exclamation-triangle
>           * MAIN TEXT
>             * You are about to create a Large Project RFI.
>           * SUB TEXT
>             * Unlike standard Requests for Information, the Applicant will not be prompted to respond to RFI line items. Instead, creating a Large Project RFI will lead to the Applicant being required to complete a \[Schedule D/Survey D/Large Project Work Survey\] project application form. If you are requesting information not required in the \[Schedule D/Survey D/Large Project Work Survey\] project application form, please create a standard RFI rather than a large project RFI.
>         * Then display the following read only fields:
>           * Project \#
>           * Category
>           * Title
>           * Applicant
>           * Event
>           * Project Type
>         * Then display a required datepicker field labeled 'RFI Deadline'
>           * This field should default in the same way that the existing modal defaults.
>         * Then display an optional text field labeled 'Additional Info'
>       * BUTTONS
>         * Create
>           * Blue button
>           * Fas fa-save icon
>           * Clicking this button should create the new Large Project RFI and take the user to the details page for that RFI outlined in&nbsp;**PBI 46518**
>           * Ensure we write an action log to the Project indicating this change.
>         * Cancel
>           * White button
>           * Fas fa-ban icon
>           * Close the modal