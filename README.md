# Connections Components - Documentation

**The HCL Connections documentation has been updated to include the information in this repository for customizing the Connections 8.0 user interface (UI). Please refer to the help topic [Customizing the user interface](https://opensource.hcltechsw.com/connections-doc/v8-cr3/admin/customize/t_admin_common_customize_main.html) for details. To share information or ask questions on customizing the user interface, refer to the [Connections community forum](https://support.hcltechsw.com/community?id=community_forum&sys_id=f2165d261b3dbf00c48197d58d4bcbb8).**

This git repository contains details and descriptions on the Connections UI components and styles for customizing them.

It serves as a baseline for developers to understand how common areas within the UI/UX should be understood and designed. The primary purpose is to achieve consistency across the various applications and features that Connections provides.

The content within this repository works in tandem with the [HCL Design System](internal-link-redacted). Given the historic growth of the tool, not all areas can be redesigned via the design system. The Connections components align whereever possible but employ a different look and feel in some areas as well.

If something is not defined in this document, it either still needs to be (reach out to the [CNX 8 UI](internal-link-redacted) Teams channel / through Git for any findings), or by default aligns with the design system. 

## Content
The following sections are available within this documentation:
- ### [Main Areas](./main-areas/)
  - Information around the main areas that exist within the Connections UI
- ### [Components](./components/)
  - An overview and details around the different components and main areas defined and used within Connections
- ### [Color Codes](./color-codes/)
  - Information around color codes to use within Connections
- ### [Font Styles](./font-styles/)
   - Information around font sizes, colors, weights and types to use within Connections
- ### [Icons](./icons/)
   - Information around the icons available to use within Connections
- ### [Custom Styles](./custom-styles/)
   - Details on the custom style properties available to customize the theme/look and feel of the Connections UI
- ### [Custom Config Extensions](./custom-config-extensions/)
   - An overview of and samples for the available configuration extensions that allow customization or theming of components
- ### [Impact on Legacy Customizations](./impact-on-legacy-customizations/)
   - Due to the nature of implementation for new UI components, some existing customizations will be ignored in the new Connections 8 UI. This section provides some details and considerations around this area.
