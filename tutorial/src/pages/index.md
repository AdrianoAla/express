---
sidebar_position: 1
---

# Uniweb Express


[Uniweb CMS](https://uniwebcms.com) is a **web engine** with advanced built-in intelligence to manage rich data and build websites from templates. The logic that is necessary for creating the user interface of a website exists at the level of **web components** and the underlying power of the web engine.

Creating a **website template** requires no technical knowledge because there is no coding involved. A template is simply a configuration profile that guides the process of building a website automatically. That automated process is what we call a **self-building website**. In short, a website template specifies the web components that are required for a self-building website.

**Uniweb Express** is a component library of low-level and general-purposed web components that can be used to create collections of higher-level and/or specialized components.

## Designing for self-building websites

One of the main goals of the Uniweb engine is to provide the information that web components need to achieve their visual results without needing any input from the owner of a website. For example, a navigation bar component (**navbar**) may need information about the page structure of the website and the active webpage.

The engine has access to both the template and the website data so it can provide information about the structure of the site and how its current data fits into it. We can illustrate this concept by continuing the above example of a **navbar**. When rendering a navbar, we not only need to know the page structure of the site but also which pages currently have meaningful information so that the navbar can show menu links that only point to them. For example, a template for a personal website may define a page that shows a list of projects to which the website owner belongs. Some users of the template may indeed have projects to show but other may not. Whether the navbar shows a Projects menu or not depends on whether the website has projects to show or not.

The conditional inclusion of navbar menus presents an interesting problem because the main logic for rendering pages is located in independent components that are unrelated to the navbar. This is a challenge that shows how the web engine is crucial for coordinating components so that the result is more than the sum of the parts.

Continuing our navbar example, we can assume that the template defines a Projects page with a component that requests its input data to be the linked projects of the website's main content. Because the web engine is aware of this dependency, it can make it use of it and expose whether the Projects page has projects to show or not. In turn, the navbar can use the information provided by the engine to decide whether a Projects menu option is necessary or not.

In summary, the engine allows us to connect the abstract definition of a website structure and dependencies with the concrete data instantiation of a specific website in a way that helps us have a complete view of the site when rendering its navbar.

## The Express Library

**Uniweb Express** is an opinionated library of low-level and general-purposed web components. It includes the [Uniweb Module SDK](https://github.com/uniwebcms/uniweb-module-sdk), which is a software development kit that provides a thin wrapper around the underlying Uniweb JavaScript engine. 

The SDK and the Express library complement one another. The SDK provides a tailored and consistent API layer for the underlying web engine, which makes it suitable to be used as a dependency of several different types of component libraries. On the other hand, Uniweb Express implements React-based components with the SDK with the goal of achieving a consistent UI look and providing commonly needed small and large components.

A Uniweb Component is a React JS component whose props are 4 objects: `profile`, `block`, `page` , and `website`. The `profile` object represents the source data of a website. The `block` object contains the settings for the component, which is considered a **building block** within a webpage. The `page` object provides information about the current webpage being rendered as a sequence of buildign blocks. Finally, the `website` provides information about the entire website. Most components only need to work with the `profile` and `block` props. [Learn more about Uniweb components](https://github.com/uniwebcms/uniweb-module-sdk/blob/main/docs/components.md)
