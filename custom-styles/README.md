# Custom Styles

The Connections Custom Styles are a generic way of applying style customizations to Connections components. The core idea is that components expect and support properties to define their styling. Throughout this section, you will find names such as `--color-header`. These names translate to CSS properties used to style components, and are used instead of hard coded values to abstract convoluted selectors and simplify reasoning about changes. They are used throughout the UI components and allow adjustments of coloring to match different themes and branding requirements. In other cases sizes of elements or fonts can be defined.

The [Configuration Example](#configuration-example) provides an illustration of how these properties are expected to be defined. The [Configuration Properties](#configuration-properties) elaborate on the sample and contain a list of the various properties that are supported and that can be customized, grouped by area of responsibility or components. 

Connections provides integration points for overwriting these values in a declarative manner to adjust the look and feel of the UI.


## Custom Configuration

### Extension Type

The custom styles use the extension type `com.hcl.connections.custom.style`.

### Example

The following JSON snippet contains properties that can be used to alter the makeup of the header area:

```
{
    "style-customization": {
        "generic": {
            "--color-header": "red",
            "--color-navigation": "yellow",
            "--color-footer": "pink",
            "--color-itmbar": "cyan",
            "--size-itmbar-icon": "30px"
        },
        "top-navigation": {
            ...
        }
    }
}
```

### Properties

The `generic` object expects key value pairs that are used as overwrites to style rules contained in the base Connections UI. The values for these rules fall into different categories:
- `color` values expect a valid color value (e.g. HEX).
- `size` values expect a valid size value, e.g. in `px`. `--font-size` counts as a size value and is defined in `rem` by default.
- `font-weight` values expect a valid font weight, e.g. `400` or `bold`.
- the `font-family` value expects a valid font-family value such as `Helvetica Neue, Arial, sans-serif`.
Note: The above categories are subject to change and may be extended in the future.

The `top-navigation` object relates to elements and their positioning within the header area. See [Header Area - Custom Config Extension](../header-area/README.md#custom-config-extension) for more details. 

The below list/table outlines all currently existing properties, grouped by area of responsibility or component.

#### Font Sizes
| Property Key       | Default Value | Usage Example / Notes |
|--------------------|---------------|-----------------------|
| --font-size-xlarge | 1.5rem        | Content headlines     |
| --font-size-large  | 1rem          | Top Navigation links  |
| --font-size-medium | 0.875rem      | Most Content          |
| --font-size-small  | 0.75rem       | Captions, footnotes   |
| --font-size-xsmall | 0.625rem      | Side Navigation text  |
| --font-size-header | 1rem          | Header Area           |

#### Font Weights
| Property Key         | Default Value | Usage Example / Notes |
|----------------------|---------------|-----------------------|
| --font-weight-bold   | bold          | Header, @Mentions     |
| --font-weight-normal | 400           | Most content          |
| --font-weight-header | bold          | Header Area           |

#### Font Family
| Property Key         | Default Value                      | Usage Example / Notes |
|----------------------|------------------------------------|-----------------------|
| --font-family        | Helvetica Neue, Arial, sans-serif; | All content           |

#### Font Colors
| Property Key           | Default Value                      | Usage Example / Notes |
|------------------------|------------------------------------|-----------------------|
| --color-text-primary   | #000000                            | Primary text color (all normal text) |
| --color-text-secondary | #3D5466                            | Secondary text color (e.g. captions) |
| --color-text-blue      | #0066B3                            | **TODO** - What is this used for? |

#### Main Area Background
This section revolves around background colors and seperators (box shadow, borders) of different areas like the overall background or content areas.

| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-base-background             | #FFFFFF       | General background    |
| --color-main-background             | #FFFFFF       | Background of content item (e.g. posts) |
| --color-main-hover-background       | #E6E6E6       | Hover color for content items (where hover is applicable) |
| --color-main-box-shadow             | 0 0 0         | Box shadow (border) of content items |
| --color-main-secondary-background   | #F2F2F2       | Background color for content within content (e.g. captions) |
| --color-main-seconday-border        | #E6E6E6       | Border color for secondary content (e.g. captions) |

**Note** - The property `--color-main-box-shadow` requires the color value in rgb notation (e.g. `0 0 0`) as it adds an additional alpha value for opacity.

#### Scrollbar 
Connections uses a custom CSS based scrollbar which can be styled with the following options.

| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-scrollbar                   | #F2F2F2       | General scrollbar color |
| --color-scrollbar-thumb             | #8F8F8F       | Color of the scroll thumb / indicator |
| --color-scrollbar-thumb-hover       | #5C5C5C       | Hover color of the scroll thumb / indicator |

#### [Header Area](../main-areas/header-area)
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-header                      | #0D264D       | Background color |
| --color-header-text                 | #FFFFFF       | Color of text in the header area |
| --size-header-image-height          | 30px          | Height of the header logo, scales both height and width |
| --size-header-spacing               | 20px          | Spacing between elements within the header area |

#### [Side Navigation](../main-areas/side-navigation)
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-navigation                  | #14356A       | Background color |
| --color-navigation-selected         | #01539B       | Background color of active/selected option |
| --color-navigation-text             | #FFFFFF       | Side navigation text color |

#### [Third Level Navigation](../main-areas/third-level-navigation)
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-third-navigation            | #f1f1f1       | Background color |
| --color-third-navigation-selected   | #d5d5d5       | Background color of active/selected option |
|  --color-third-navigation-text      | #000000       | Third level navigation text color |

#### [Important To Me (ITM) Bar](../main-areas/itm-bar)
| Property Key                        | Default Value | Usage Example        |
|-------------------------------------|---------------|----------------------|
| --color-itmbar                      | #F2F2F2       | Background color |
| --size-itmbar-icon                  | 48px          | Size of profile icons within the ITM bar |

#### [Footer](../main-areas/footer)
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-footer                      | #0D264D       | Background color |
| --color-footer-text                 | #FFFFFF       | Text color |
| --color-footer-text-hover           | #D3D9DE       | Text color on hover (links) |

#### [Search](../main-areas/search)
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-search                      | #FFFFFF       | Background color |
| --color-search-text                 | #000000       | Text color |
| --color-search-selected             | rgba(0, 0, 0, 0.04) | Background color on hover |

#### Links
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-link                        | #01539B       | Link color |
| --color-link-hover                  | #092B51       | Hover color for links |

#### Buttons
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-button                      | #01539B       | Background color |
| --color-button-hover                | #092B51       | Background color on hover |
| --color-button-text                 | #FFFFFF       | Text color |
| --color-button-disabled             | #E6E6E6       | Background color for disabled buttons |
| --color-button-disabled-text        | #ADADAD       | Text color for disabled buttons |

#### Notifications / Snackbars
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-info-message                | #273641       | Background color |
| --color-info-message-text           | #FFFFFF       | Text color |
| --color-info-message-link           | #2ABDEA       | Color of links |
| --color-info-message-link-hover     | #14A1DE       | Hover color of links |

#### [Banner](../main-areas/banner)
The banner uses different styles depending on the available severity levels (success, info, warning or error).

**Severity: Success**
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-admin-banner-success        | #E4FDED       | Background color |
| --color-admin-banner-success-text   | #000000       | Text color |

**Severity: Info**
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-admin-banner-info           | #F9EEFF       | Background color |
| --color-admin-banner-info-text      | #000000       | Text color |

**Severity: Warning**
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-admin-banner-warning        | #FFF6E2       | Background color |
| --color-admin-banner-warning-text   | #000000       | Text color |

**Severity: Error**
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-admin-banner-error          | #FFF2F2       | Background color |
| --color-admin-banner-error-text     | #000000       | Text color |

#### Modals
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-modal-header                | #FFFFFF       | Header background color |
| --color-modal-header-text           | #000000       | Header text color |

#### Badges
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-badge                       | #C10C0D       | Background color |
| --color-badge-text                  | #FFFFFF       | Text color |

#### Chips
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-chip                        | #E6E6E6       | Background color |
| --color-chip-text                   | #000000       | Text color |
| --color-chip-close                  | #ADADAD       | Background color of close icon |
| --color-chip-close-hover            | #8F8F8F       | Background color of close icon on hover |

#### Tabs
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
| --color-tab                         | #FFFFFF       | Background color |
| --color-tab-text                    | #3D5466       | Text color |
| --color-tab-text-selected           | #01539B       | Text color of active/selected option |
| --color-tab-border-selected         | #0D264D       | Border/highlight of active/selected option |


#### Toggles
| Property Key                        | Default Value | Usage Example / Notes |
|-------------------------------------|---------------|-----------------------|
|  --color-switch-primary             | #6e9bc2       | Active toggle background color |

**TODO** - add colors for active toggle button and disabled background/toggle