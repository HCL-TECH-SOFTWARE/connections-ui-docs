# Impact on Legacy Customizations

With the Connections 8 UI redesign, some customization options will not work the way they used to. Generally, all existing and documented customization options are still available (see our [HCL Connections Documentation - Customizing](https://help.hcltechsw.com/connections/v7/admin/customize/c_customize_overview.html)).

Some areas, however, will be ignored due to the nature of implementation for new UI components, e.g. the switch to a new navigation area.

## Upgrade Considerations

For a gauge of what can be expected to work vs. what may need to be upgraded / removed, we differentiate between the below three categories:

### Functional / Behavioral

Most functional customizations are still valid and can be expected to work. This does not apply to areas that are not available or visible anymore within the UI, e.g. the previous header bar. 

JSP and JavaScript customizations may be subject to updates. I.e. if there are existing customizations in your system, they need to be verified against the respective files and code fragments in the core of the new 8.0 release. One candidate where changes can be expected is e.g. the Profiles application. 

In general, JSPs and JavaScript (OSGi) modules are still heavily used and can be adjusted the same way as it worked in previous versions.

### Cosmetic

Most cosmetic customizations are still valid, but they may appear differently now due to the worked UI and respective changes. This does not apply to areas that are not available or visible anymore within the UI, e.g. the previous header bar. 

CSS customizations in particular may be invalidated due to the nature of UI changes and consolidated styles. The suggested way of applying style customizations is outlined in [Custom Styles](../custom-styles/).

**Note** The UI update may result in breaking UI based automation (e.g. DOM driven testing). Depending on the implementation and required elements, this may require changes to reflect the new UI makeup. 

### Globalization

When it comes to localization and customization of text, the customizations are generally still valid. The 8.0 release introduced new strings and replaces old ones in various areas, e.g. Homepage and Profiles, so this may need to be merged into existing customization property files.

Many of the new UI components now also use a different foundation for managing translations, e.g. the [Side Navigation](../main-areas/side-navigation/). For the new components, the [Custom Config Extensions](../custom-config-extensions/) can be used to apply new translations as is documented within the respective areas / components.

### Testing 7.0 vs 8.0 changes

Heavily customized deployments may need extra time or testing capabilities to ensure customizations are working properly and are restored in the new UI. For a limited time, the 7.0 UI can be enabled to ease the transition period for users. 

By default, the 8.0 UI is enabled. To change this, set the following generic property within the LotusConnections-config.xml:
```
<genericProperty name="ics.ui.isCNX8UXEnabled">false</genericProperty>
``` 
**Note** This update requires a server restart (and sync of nodes if using a Network Deployment environment) to take effect.
**Note** This property and turning back to the 7.0 UI will not be supported indefinitely. Currently this is planned to be supported until Q2 2023 but this may be subject to change.