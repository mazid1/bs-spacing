# bs-spacing

Generate Boostrap like CSS spacing classes using SASS.

## Bootstrap Classes: A Closer Look

According to the documentation of [Bootstrap 4](https://getbootstrap.com/docs/4.1/utilities/spacing/) its spacing classes have the following format:

The classes are named using the format `{property}{sides}-{size}` for `xs` and `{property}{sides}-{breakpoint}-{size}` for `sm`, `md`, `lg`, and `xl`.

Where `property` is one of:

- `m` - for classes that set `margin`
- `p` - for classes that set `padding`

Where `sides` is one of:

- `t` - for classes that set `margin-top` or `padding-top`
- `b` - for classes that set `margin-bottom` or `padding-bottom`
- `l` - for classes that set `margin-left` or `padding-left`
- `r` - for classes that set `margin-right` or `padding-right`
- `x` - for classes that set both `*-left` and `*-right`
- `y` - for classes that set both `*-top` and `*-bottom`
- blank - for classes that set a `margin` or `padding` on all 4 sides of the element

Where `size` is one of:

- `0` - for classes that eliminate the `margin` or `padding` by setting it to `0`
- `1` - (by default) for classes that set the `margin` or `padding` to `$spacer * .25`
- `2` - (by default) for classes that set the `margin` or `padding` to `$spacer * .5`
- `3` - (by default) for classes that set the `margin` or `padding` to `$spacer`
- `4` - (by default) for classes that set the `margin` or `padding` to `$spacer * 1.5`
- `5` - (by default) for classes that set the `margin` or `padding` to `$spacer * 3`
- `auto` - for classes that set the `margin` to auto

## Goal Of This Project

Our focus is to generate all the css classes of the format `{property}{sides}-{size}`.

For example:

1. `m-0` to `m-5` and `m-auto`
2. `p-0` to `p-5`
3. `mt-0`, `mb-0`, `ml-0`, `mr-0` to `mt-5`, `mb-5`, `ml-5`, `mr-5` and `mt-auto`, `mb-auto`, `ml-auto`, `mr-auto`
4. `pt-0`, `pb-0`, `pl-0`, `pr-0` to `pt-5`, `pb-5`, `pl-5`, `pr-5`
5. `mx-0` to `mx-5` and `my-0` to `my-5` and `mx-auto`, `my-auto`
6. `px-0` to `px-5` and `py-0` to `my-5`

Notice, we are omitting `{property}{sides}-{breakpoint}-{size}` pattern, which is not in the scope of this project.

## Usage

If your project setup supports scss file, then you can copy the `_spacing.scss` file from the `src` directory into your project and import this file into your root style file using [`@use`](https://sass-lang.com/documentation/at-rules/use) rule.

```scss
// styles.scss file, in the same directory of _spaces.scss
@use "./spaces";
```

If you need compiled css, then you can copy the generated `spacing.css` file from the `dist` directory. However, you can install [SASS](https://sass-lang.com/guide) on your machine and use the following command to generate `spaces.css` file by yourself.

```
sass _spaces.scss spaces.css
```
