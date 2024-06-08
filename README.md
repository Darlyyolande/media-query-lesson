### Media Queries

The **CSS Media Query** gives you a way to apply CSS only when the browser and device environment matches a rule that you specify, for example "viewport is wider than 480 pixels". Media queries are a key part of responsive web design, as they allow you to create different layouts depending on the size of the viewport, but they can also be used to detect other things about the environment your site is running on, for example whether the user is using a touchscreen rather than a mouse. In this lesson you will first learn about the syntax used in media queries, and then move on to use them in a working example showing how a simple design might be made responsive.

#### Basic Syntax

A media query for `min-width` and `max-width` is written like this:

```css
@media screen and (min-width: 768px) {
	/* CSS rules for viewports wider than or equal to value */
}
@media screen and (width >= 768px) {
	/* CSS rules for viewports wider than or equal to value */
}

@media screen and (max-width: 1250px) {
	/* CSS rules for viewports narrower than or equal to value */
}

@media screen and (width <= 1250px) {
	/* This can also be written with <(less than) or >(greater than) */
}
```

#### Examples

1. **Max-Width Example**: Apply styles if the viewport width is 600px or less.

    ```css
    @media screen and (max-width: 600px) {
    	body {
    		background-color: lightblue;
    	}
    }
    ```

    This will change the background color to light blue for devices with a width of 600px or less, typically targeting mobile devices.

2. **Min-Width Example**: Apply styles if the viewport width is 768px or more.

    ```css
    @media screen and (min-width: 768px) {
    	body {
    		background-color: lightgreen;
    	}
    }
    ```

    This will change the background color to light green for devices with a width of 768px or more, typically targeting tablets and desktops.

3. **Combined Min and Max Width**: Apply styles for devices with a width between 600px and 1200px.

    ```css
    @media screen and (min-width: 600px) and (max-width: 1200px) {
    	body {
    		background-color: lightcoral;
    	}
    }
    @media screen and (600px <= width <= 1200px) {
    	/* This can also be written with <(less than) or >(greater than) */
    }
    ```

    This will change the background color to light coral for devices with a width between 600px and 1200px, covering small tablets to smaller desktop monitors.

#### Mobile-First Approach

A common strategy in responsive design is the mobile-first approach, where you start with styles for small screens and add media queries to handle larger screens.

1. **Default Styles for Mobile**: Define the default styles for mobile devices first.

    ```css
    body {
    	background-color: white;
    }
    ```

2. **Tablet and Up**: Use a `min-width` media query to apply styles for tablets and larger devices.

    ```css
    @media screen and (min-width: 600px) {
    	body {
    		background-color: lightblue;
    	}
    }
    ```

3. **Desktop and Up**: Use a `min-width` media query for desktops and larger screens.

    ```css
    @media screen and (min-width: 1200px) {
    	body {
    		background-color: lightgreen;
    	}
    }
    ```

#### Combining Media Queries

To avoid redundancy and improve maintainability, you can combine media queries within a single block.

```css
@media screen and (max-width: 600px) {
	body {
		font-size: 14px;
	}
}

@media screen and (min-width: 601px) and (max-width: 1200px) {
	body {
		font-size: 16px;
	}
}

@media screen and (min-width: 1201px) {
	body {
		font-size: 18px;
	}
}
```

Media queries with `min-width` and `max-width` are essential for creating responsive designs that adapt to various screen sizes. By using these properties, you can ensure your website provides an optimal user experience on devices ranging from mobile phones to large desktop monitors. Adopting a mobile-first approach and combining media queries efficiently will help maintain a clean and manageable stylesheet.
