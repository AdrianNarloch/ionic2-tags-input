# Ionic 2 Tags Input

An **Ionic 2** module that lets users enter and manage values in a tag/chip style UI.

## Features
- Custom labels and placeholders
- Maximum tag length restriction
- Maximum number of tags restriction
- Optional duplicate prevention
- Callbacks when a tag is added or removed


![Gif](https://github.com/sub5111/ionic2-tags-input/blob/master/tags-input-example.gif?raw=true)

## Installation

### 1. Install the npm package

```
npm install --save ionic2-tags-input
```

### 2. Import `TagsInputModule` in your app module

```typescript
import { TagsInputModule } from 'ionic2-tags-input';

@NgModule({
  ...
  imports: [
    TagsInputModule
  ]
})
```

## Usage

Bind the component to a `FormControl`/`formControlName` (Reactive Forms) or `ngModel`.

```html
<tags-input formControlName="animals"></tags-input>
```

The component value is an array of objects shaped like `{ name: string }`.

Reactive Forms example:

```typescript
public form: FormGroup = this.formBuilder.group({
  animals: [[
    { name: 'Gazelle' },
    { name: 'Cat' }
  ]]
});
```


### @Inputs / Attributes

| Name | Type | Description | Default Value |
| --- | --- | --- | --- |
| maxTags | number | Number of tags allowed. If maximum value is achieved, add button becomes disabled | N/A |
| maxWordLength | number | Maximum length of the word/sentence | N/A |
| allowDuplicates | boolean | Allow duplicates | false |
| buttonLabel | string | Add button label | Add |
| alertTitleLabel | string | The title of alert | Add item |
| alertInputPlaceholder | string | Placeholder of the input inside the alert modal | Type text |
| alertButtonLabel | string | Label of the alert button | OK |
| wordLengthRestrictionMsg | string | Text displayed if word is too long | Error: This word is too long |
| duplicatesRestrictionMsg | string | Text displayed if user is trying to make a duplicate | Error: Duplicates are not allowed |

### @Outputs

| Name | Type | Description |
| --- | --- | --- |
| onTagAdded | EventEmitter | Emitted after a tag is added |
| onTagRemoved | EventEmitter | Emitted after a tag is removed |
