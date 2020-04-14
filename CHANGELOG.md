# Tableau UI Release Notes
The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

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
