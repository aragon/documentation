# Colors

Colors in aragonUI are managed by its theming system. An aragonUI theme is a set of colors assigned to a predefined palette. All aragonUI components use colors from this palette, making it possible to swap the theme for another one dynamically. aragonUI includes two themes by default, _light_ and _dark_, but any other can be provided.

## Usage <a href="#usage" id="usage"></a>

The theme palette can be obtained in a component by using the `useTheme()` hook:

```jsx
function App() {
  const theme = useTheme()
  return (
    <Main>
      <p
        css={`
          color: ${theme.negative};
        `}
      >
        Negative content
      </p>
    </Main>
  )
}
```

## Notes <a href="#notes" id="notes"></a>

Colors meant to be applied on text are indicated using the _Content_ suffix. The reason why it is not using _Text_ is because these also apply to other outline content like icons.

When a color like _foo_ is followed by a color named _fooContent_, it generally means that _foo_ should be used as a background color for _fooContent_.

Gradients are defined using the _Start_ and _End_ suffixes.

Colors don’t include opacity. When using aragonUI’s `useTheme()`, the `.alpha(0.5)` method can be used on any color. It will apply the desired opacity and return the result as a CSS color using the `rgba()` syntax.

## Palette groups <a href="#palette-groups" id="palette-groups"></a>

This section describes the palette colors and how they should be used. The groups are created based on how they relate to each other.

### Base <a href="#base" id="base"></a>

The colors defined in this group are either used by default (border, content, overlay), or on the base layer (background).

#### _**background**_

The base layer on which apps are being rendered.

#### _**border**_

The border color used everywhere by default, except in specific cases like _controlBorder_.

#### _**overlay**_

The color used for overlays. Some components using an overlay color are SidePanel or Modal.

#### _**content**_

The base color for text and outline content. To be used over _background_.

#### _**contentSecondary**_

Secondary color for text and outline content. To be used over _background_.

#### _**link**_

Used as a base color for links.

#### _**focus**_

The color for focus rings.

#### _**accent**_

The _accent_ color can be used to put an emphasis on a component or a certain part of a component, without any specific semantic.

#### _**accentContent**_

To be used for text and outline content over _accent_.

#### _**accentStart**_** / **_**accentEnd**_

This is the gradient equivalent of _accent_.

### Surface <a href="#surface" id="surface"></a>

The main surface as defined by aragonDS and its different states. This group of colors is used by components providing surfaces: Box, DataView, the default Button, the Slider handle, and many more.

#### _**surface**_

The background color used for surfaces.

#### _**surfaceContent**_

The primary color used for text and outline content over _surface_.

#### _**surfaceContentSecondary**_

The secondary color used for text and outline content over _surface_.

#### _**surfaceIcon**_

This color is generally used for icons over _surface_. Note: in some cases, icons over _surface_ are also using _surfaceContent_ or _surfaceContentSecondary_.

#### _**surfaceUnder**_

This is used as a background base for surfaces that appear to be at a lower level than the parent _surface_ itself. For instance, the DataView component is using this color for its entry expansion, which opens underneath the primary surface provided by DataView.

#### _**surfaceOpened**_

Communicates that a _surface_ is being “opened”, generally revealing a surface using _surfaceUnder_ underneath. The DataView component is using this color for the side border of its entry expansion.

#### _**surfaceSelected**_

Indicates that a _surface_, or a part of it, is being selected. This is the color DataView is using to indicate that an entire row is selected.

#### _**surfaceHighlight**_

Indicates that a _surface_, or a part of it, is being highlighted. This color could be used to reflect a hover or focused state.

#### _**surfacePressed**_

Indicates that a _surface_, or a part of it, is being pressed − either by a pointer or a touch event.

### Info <a href="#info" id="info"></a>

Used to indicate informative content in general.

#### _**info**_

This info color is generally stronger than _infoSurface_. It should be used for icons, borders, etc.

#### _**infoSurface**_

The surface info color, generally softer than _info_. It should be used for background colors.

#### _**infoSurfaceContent**_

To be used for text and outline content over _infoSurface_.

### Feedback <a href="#feedback" id="feedback"></a>

Used to signal feedback, in the broad sense. For instance, this set of colors is used to show the status of a transaction in the signing panel.

#### _**feedbackSurface**_

Use this color as a background color for feedback.

#### _**feedbackSurfaceContent**_

The primary color to be used for text and outline content over _feedbackSurface_.

#### _**feedbackSurfaceContentSecondary**_

The secondary color to be used for text and outline content over _feedbackSurface_.

### Warning <a href="#warning" id="warning"></a>

Used to indicate warnings.

#### _**warning**_

This warning color is generally stronger than _warningSurface_. It should be used for icons, borders, etc.

#### _**warningSurface**_

The surface warning color, generally softer than _warning_. It should be used for background colors.

#### _**warningSurfaceContent**_

To be used for text and outline content over _warningSurface_.

### Help <a href="#help" id="help"></a>

Used for elements related to helping the user.

#### _**help**_

This help color is generally stronger than _helpSurface_ and should be used for icons, borders, etc.

#### _**helpContent**_

To be used for text and outline content over _help_.

#### _**helpSurface**_

This help color is generally softer than _help_ and should be used for background colors.

#### _**helpSurfaceContent**_

To be used for text and outline content over _helpSurface_.

### Positive <a href="#positive" id="positive"></a>

Used to communicate something positive. It can be used for successful operations, but also for other things like voting “Yes”.

#### _**positive**_

Use this color to communicate positive information (e.g. success, an action to vote yes).

#### _**positiveContent**_

To be used for text and outline content over _positive_.

#### _**positiveSurface**_

A softer _positive_, to be used when a large amount of information needs to be communicated.

#### _**positiveSurfaceContent**_

To be used for text and outline content over _positiveSurface_.

### Negative <a href="#negative" id="negative"></a>

Used to communicate something negative. It can be used for errors, but also for other things like voting “No”.

#### _**negative**_

Use this color to communicate negative information (e.g. error, an action to vote no).

#### _**negativeContent**_

To be used for text and outline content over _negative_.

#### _**negativeSurface**_

A softer _negative_, to be used when a large amount of information needs to be communicated. For instance, the Info component uses it as a background color in error mode.

#### _**negativeSurfaceContent**_

To be used for text and outline content over _negativeSurfaceContent_.

### Tag <a href="#tag" id="tag"></a>

This set of colors is used by the Tag component and its different modes.

#### _**tagIdentifier**_

Used to identify or label a subject.

#### _**tagIdentifierContent**_

To be used for text and outline content over _tagIdentifier_.

#### _**tagNew**_

Used to indicate that a subject is new, or updated.

#### _**tagNewContent**_

To be used for text and outline content over _tagNew_.

#### _**tagIndicator**_

Used for indicators in the general sense.

#### _**tagIndicatorContent**_

To be used for text and outline content over _tagIndicator_.

#### _**tagActivity**_

Used to represent some activity that happened, like a number of notifications.

#### _**tagActivityContent**_

To be used for text and outline content over _tagActivity_

### Badge <a href="#badge" id="badge"></a>

This colors are used for badge-like components: IdentityBadge, AppBadge, etc.

#### _badge_ <a href="#badge-2" id="badge-2"></a>

The background color of badge-like components.

#### _badgeContent_ <a href="#badgecontent" id="badgecontent"></a>

To be used for text and outline content over _badge_.

#### _badgePressed_ <a href="#badgepressed" id="badgepressed"></a>

The pressed state of _badge_.

### Floating <a href="#floating" id="floating"></a>

Floating elements, like tooltips.

#### _floating_ <a href="#floating-2" id="floating-2"></a>

The background color of a floating element.

#### _floatingContent_ <a href="#floatingcontent" id="floatingcontent"></a>

To be used for text and outline content over _floating_.

### Controls <a href="#controls" id="controls"></a>

Colors related to controls, that could be used in forms or elsewhere.

#### _**hint**_

Used for hints (or placeholders) inside of text input or similar components.

#### _**selected**_

Indicates a selection in the broad sense.

#### _**selectedContent**_

To be used for text and outline content over _selected_.

#### _**selectedDisabled**_

Indicates a selection in the broad sense, when disabled (non-interactive).

#### _**disabled**_

The background color of disabled components like Button.

#### _**disabledContent**_

The text or outline content to be used over _disabled_.

#### _**disabledIcon**_

This color is generally used for icons over _disabled_. Note: icons over _disabled_ could also be using _disabledContent_.

#### _**control**_

Used as a background color for some control components like Checkbox, Radio or Switch.

#### _**controlBorder**_

Used as a border color for some control components like Checkbox, Radio or Switch.

#### _**controlBorderPressed**_

Used as a border color for the pressed state of some control components like Checkbox, Radio or Switch.

#### _**controlDisabled**_

The background color for the disabled state of some control components like Checkbox, Radio or Switch.

#### _**controlSurface**_

This is used as a surface color for elements of control components that appear at an upper level. For instance, the Switch component is using this color for its handle.

#### _**controlUnder**_

This is used as a background base for elements of control components that appear to be at a lower level. For instance, the Switch component is using this color for its inner base.

### Colors <a href="#colors" id="colors"></a>

These colors can be used when a color is needed for its semantics. An example could be a chart using a red and a blue curve. Even if their theme is different, two users should still be able to refer to these by using the terms “red” or “blue”.

Themes are free to implement their own variation of these colors, but they should respect the naming (e.g. _green_ can vary, but should use a color that is commonly accepted to be “green”).

Available color names:

* _green_
* _yellow_
* _red_
* _blue_
* _brown_
* _purple_
