# Tableau UI Release Notes
The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## 3.10.0
- Documentation code samples updated to use standard React hooks.
- Improved emitted type definitions which depend on `Omit`.
- `ColorGrid`
  - New component!
- `Disclosure`
  - New component!
- `SideTabs`
  - Prop `onChangeTab` deprecated in favor of `onTabChange`, for naming consistency.

## 3.9.0
- `Button`, `DropdownSelect`, `Stepper`, `TextArea`, `TextField`
  - Updated border color.
- `SideTabs`
  - New component!
- `Spinner`
  - Prop `alt` is now required because this package does not include localized strings by default.
- `TextFieldGroup`
  - Minor revisions to styling.

## 3.8.0
- `Badge`
  - New component!
- `Button`
  - Added `lowEmphasisDark` kind.
- `Button`, `Checkbox`, `DropdownSelect`, `Radio`, `Stepper`, `Tabs`, `TextArea`, `TextField`, `ToggleSwitch`
  - Improved accessibility with with higher color contrast ratios across all states as well as an updated focus indicator.
- `Button`, `Tabs`, `TextLink`, `ToggleSwitch`
  - Updated focus indicators to use `:focus-visible`
- `Stepper`
  - Corrected props typedefs to allow all native `<input>` attributes.
- `Sticker`
  - New component!
- `Tabs`
  Corrected a keyboard navigation bug when using `'manual'` activation mode.
- `TextArea`
  - Added `autoHeight` prop, which causes the `<textarea>` element to grow (or shrink) to fit its content as the user types.
- `TextArea`, `TextField`
  - Adjusted wrapping behavior of validation messages.
- `TextFieldGroup`
  - New component!
- `TextLink`
  - Updated colors and changed hover state to underline.

## 3.7.0
- `Stepper`
  - Behavior of the up/down buttons has been corrected in the case that the user has edited, but not yet confirmed, the field value.

## 3.6.0
- (Corrects an error that only affected Tableau's internal systems.)

## 3.5.0
### Fixes
- `Spinner`
  - Removed previous incorrect advice which suggested the use of `aria-busy`.
- `TextField`
  - `type` attribute is now explicitly defaulted to `'text'`, to allow for easier querying.
- `ToggleSwitch`
  - Fixed height of right-aligned switches to match left-aligned switches.

## 3.4.0
### Features
- `TextLink`
  - Deprecated `lowEmphasis` kind in favor of `lightweight`. Added new `inline` kind.

- `ToggleSwitch`
  - New component!

### Fixes
- `TextField`
  - A field with unspecified width no longer grows when the clear button is shown.

## 3.3.0
### Features
- Added `-webkit-` vendor prefixing for flexbox properties, for better compatibility with certain components of Tableau Desktop.

## 3.2.0
### Features
- `Checkbox`
  - Updated visual style of `indeterminate` checkboxes.

### Fixes
- Fixed invisible text on disabled input elements in Safari.
- Pinned the `typestyle` dependency to version `2.0.4` to ensure compatibility with IE11.
- `Spinner`
  - Fixed `alt` prop getting applied to the wrong element.
- `Stepper`
  - Allow inputting a partial value which falls outside the min/max range.
- `TextField`/`TextArea`/`DropdownSelect`
  - Allow long messages to wrap to multiple lines when container is width-constrained.
  - Improved vertical alignment of validation state icons.

## 3.1.0
### Features
- `Stepper`
  - Allow `value` to be `undefined` when disabled.

## 3.0.0
Tableau 2019.4 includes a visual refresh of some UI elements for improved Accessibility. This release of Tableau UI includes updates to match. **In addition, Tableau UI now requires React 16.8 or above.**

- `Button`
  - Deprecated `kind` values: `filled` and `blackText` have been internally remapped to `outline`.
  - New prop: `density` for adjusting padding in a consistent manner.
- `Checkbox` and `Radio`
  - Updates to focus indicator implementation for consistency and clarity.
  - Internal DOM structure changed.
- `DropdownSelect`
  - New prop: `label`.
  - `outline`, `line`, and `text` styles now share the same arrow icon. (Icon of `icon` style is unchanged.)
- `Stepper`
  - New prop: `label`.
  - Undocumented props are now passed to the `<input>` rather than the container `<div>`. This is important for e.g. `aria-labelledby`.
  - Documentation: `disabled` is no longer listed explicitly in documentation, as it is identical to the native `<input>` prop.
- `TextField`
  - New prop: `valid` used to set validation state of the field, with accompanying visual styling and ARIA metadata.
  - New prop: `message` replaces `errorMessage` for displaying a message under the field -- can be combined with `valid` to style as a validation message.
  - Changed props: `id` and `style` are now passed to the `<input>`, not the root `<div>`.
  - Removed prop: `errorMessage`. Instead, set `message='some error message' valid={false}`.
  - The "floating placeholder/label" behavior particular to the `line` kind has been removed. Placeholder/label behavior is now consistent across kinds and usages.
  - Documentation: `placeholder`, `type`, and `value` are no longer listed explicitly in documentation, as they are identical to their respective native `<input>` props.

### Features
  - Added `TextArea` component
  - Added `TextLink` component
  - Added `alt` prop to `Spinner`

### Fixes
  - `Checkbox`, `DropdownSelect`, `Radio`, and `TextField`: when `id` prop is provided, it is now correctly passed to the form element. When `id` prop is not provided, these components will auto-generate an id for internal use (as before).
  - `TextField` no longer shows the clear button when disabled.

## 2.2.1
### Fixes
- [#21](https://github.com/tableau/tableau-ui/issues/21): "TS Property '...' does not exist on type"
- `TextField`:
  - no longer reserves space for a label when `label` prop is `undefined`.
  - no longer shows an inner shadow in iOS Safari.
  - error label text is now 10px (was 9px).
  - clear button behavior is improved and alignment corrected.
- `Button`:
  - Kinds have been simplified to `primary`, `outline`, and `destructive`.
  - *Deprecated* kinds: `attentionRed`, `blackText`, `filled`, and `filledGreen`. For now these kinds are internally remapped to the new kind names, but will be removed in a future release. Please migrate per the jsdoc documentation.
- `DropdownSelect` border is now green when focused (matching `TextField`).
- Internally generated `id` attributes are now seeded rather than starting from 0.
- Corrected several documentation typos.

## 2.2.0
### Features
- [#15](https://github.com/tableau/tableau-ui/issues/15): Added `Stepper` Component

### Fixes
- [#20](https://github.com/tableau/tableau-ui/issues/20): `TextField` with numeric value 0 displays 0 above the input

## 2.1.0
### Features
- [#12](https://github.com/tableau/tableau-ui/issues/12): `Button`, `Checkbox`, `DropdownSelect`, `Pill`, `Radio`, `Spinner`, and `TextField` now properly [Forward Refs](https://reactjs.org/docs/forwarding-refs.html).
  - Because `ref` was previously non-functional on these components, this change is considered additive rather than breaking.

## 2.0.3
### Fixes
- Added missing CHANGELOG.md entries

## 2.0.2
### Fixes
- Added missing README.md to npm package

## 2.0.1
### Fixes
- Restored documentation for `className`, `id`, and `style` on `TextField` due to particular behavior on that component.
- Improved the appearance of the `Spinner` graphic.
- `DropdownSelect` arrow icon will now remain when passing a `background` style override.
- Left-Justified Tabs can expand past their container
- [#11](https://github.com/tableau/tableau-ui/issues/11): `Pill` component is not being exported

## 2.0.0
### BREAKING
- Renamed `onChange` callback on `TabsProps` to `onTabChange` to avoid shadowing native HTML `onChange` event.
- When `aria-label` is provided on `TabsProps`, it is now applied to the root container rather than the tabs list.

### Features
- Added `Pill` Component

### Fixes
- Removed extraneous documentation for native props (e.g. `className`, `id`, `style`).

## 1.0.4
### Fixes
- Undefined `onChange` Prop on `Tabs` Throws Error when Changing Selected Tab

## 1.0.3
### Fixes
- `TextField` label margin displays even without label

## 1.0.2
### Fixes
- Misalignment of Clear Button in `TextField`

## 1.0.1
### Features
- Added `Tabs` Component
- Added `Spinner` Component
- Added `Button` Component
- Added `Checkbox` Component
- Added `Radio` Component
- Added `TextField` Component
- Added `DropdownSelect` Component
