---
title: "Unlocking the Secrets of Server-Driven UI: A Thrilling Adventure"
seoTitle: "What is Server Driven UI?"
datePublished: Mon Feb 26 2024 16:48:17 GMT+0000 (Coordinated Universal Time)
cuid: clt36agbh000508lfbeum17jz
slug: unlocking-the-secrets-of-server-driven-ui-a-thrilling-adventure
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708966056325/5619b9b4-2f4e-42cd-bf22-ec07220b98d8.png
tags: app-development, javascript, web-development, ui, server-driven-ui

---

Server-driven UI (SDUI) represents a cutting-edge approach embraced by industry leaders such as Airbnb and Lyft, where the server takes the reins in constructing mobile app user interfaces. This innovative method not only unlocks fresh opportunities but also tackles key issues inherent in the conventional process of native mobile app development. To comprehend the workings of server-driven UI, it's essential to first delve into the current landscape of mobile app development.

## How did it start?

In the traditional mobile app development paradigm, developers craft the layout and presentation of the user interface, which is then integrated into the app and submitted to the App/Play Store. Following submission, Apple or Google reviews the app before making it accessible for users to install. The dynamism of user interfaces in these apps is achieved by decoupling the UI from the data it presents. While the user interface constitutes a part of the app's binary, the data is typically sourced from a server and incorporated into the UI.

To illustrate, consider a standard listing screen that showcases a collection of products. A developer would construct a list view featuring a template for each product's display. In this instance, the template might include the product's thumbnail, title, and price.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708963605483/ab04dc81-449a-44b4-a4d7-5e53429069d6.jpeg align="center")

Upon presenting the listing screen to the user, the application dynamically retrieves a roster of products from a remote server to populate and showcase on the screen. This mechanism ensures that the displayed content is always current and can be updated seamlessly by fetching the latest data from the server.

```json
[
    {
      "thumbnail": "https://images.example.com/instinct.jpg",
      "title": "Rocky Mountain Instinct",
      "description": "Stable and aggressive, the Instinct is..."
      "price": 6999.99,
      "rating": 4.8,
      "sale": false,
      "featured": false
    },
    {
      "thumbnail": "https://images.example.com/stumpjumper.jpg",
      "title": "Specialized Stumpjumper",
      "description": "The Stumpjumper brings all-new..."
      "price": 3178.99,
      "rating": 4.3,
      "sale": true,
      "featured": false
    },
    //...
]
```

The list of products, the data, is combined with the UI built by the developer and transformed into a list view.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708963820505/43b3b2da-072c-4ec6-80da-c6d968de2e56.jpeg align="center")

## The Release Process

Now let's imagine after launching our listing screen we decide to add the product's star rating to each row and give a special treatment to sale items.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708963924591/8155d6eb-2af8-4c47-9ede-614f38c5f2f8.jpeg align="center")

The procedure for implementing changes to the user interface involves a comprehensive release cycle. This sequence unfolds as follows:

1. Developers encode the necessary changes to the UI.
    
2. Testers assess and review the modifications.
    
3. A fresh version of the app is submitted to the App/Play Store.
    
4. Apple/Google conducts a review and grants approval.
    
5. Users proceed to update their applications to the latest version.
    

It's noteworthy that for a typical app supporting both iOS and Android platforms, this release cycle must be executed separately for each platform, often necessitating different sets of developers.

However, the challenge arises when, by the time these modifications reach users' devices, there is a subsequent desire to introduce additional alterations. For instance, a new objective may be to showcase featured products at the top of the list within a horizontal scroll container. This iterative process underscores the need for a more agile and responsive approach to UI updates.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708964080546/5b619fb5-6418-4c69-8ee2-87eb47edd501.jpeg align="center")

Indeed, the repetitive cycle of development, testing, and awaiting approval on both platforms extends the timeline significantly. Even for seemingly straightforward modifications, such as introducing a horizontal scroll container for featuring products at the top of the list, the process demands weeks or even months before these changes are reflected in the App/Play Store. Furthermore, the additional hurdle emerges post-release, as user adoption of the new version becomes a requisite for them to experience the updated features. This delay in reaching end-users underscores the inherent sluggishness of the traditional release cycle in promptly delivering and implementing user interface enhancements.

## **The Dilemma Unveiled: Shackles of the Release Cycle**

The necessity to run through a full release cycle for even simple UI changes comes with a few problems. First, it slows down experimentation and iteration. The overhead of the release cycle means we are waiting long periods before understanding how users are responding to each change we make to the UI. Because of this, many companies fall back to testing prototypes instead of learning from live users. In an ideal world, we could A/B test our user interfaces but the release cycle makes this difficult. Second, as Ryan Brooks from Airbnb put it, it creates a versioning problem. Each time we release a new version of our app we have to wait for our users to update it. Some will update right away, some will take their time and some won't update at all. This creates a fragmented user experience.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708964358618/31c4ed67-aaa8-45c0-a86a-900af4010fdd.jpeg align="center")

Furthermore, the challenge of maintaining a consistent user interface is exacerbated by the need to independently develop changes for both iOS and Android platforms. Each platform adheres to distinct UI paradigms, necessitating careful consideration to ensure coherence. It is not uncommon for the outcomes to diverge between iOS and Android versions due to their inherent differences.

Compounding this, there is a notable discrepancy in the frequency of app updates among users on iOS and Android. iOS users typically adopt updates more promptly than their Android counterparts, contributing to increased fragmentation in the user experience. This disparity in update rates further complicates efforts to maintain a uniform and synchronized user interface across diverse devices and platforms.

## **The Dance of Liberation: How Server-Driven UI Unfurls Its Magic**

With the traditional development process, the user interface is embedded in the app which makes it inflexible and difficult to update. But the data is fetched from a remote server. The data displayed in the app is always up-to-date and can be modified at any time through a backend system. What if we could apply the same technique we use for data to the user interface itself?

> **What if we could apply the same technique we use for data to the user interface itself?**

Introducing server-driven UI (SDUI), where the user interface within the app serves as a blank canvas. In this implementation, the app operates with the understanding that it will be rendering a listing screen but refrains from making any presumptions about the visual design. Instead, the app initiates a request to the server, which in turn furnishes both the UI structure and the accompanying data in a unified response. This marks a departure from the conventional method, providing a more flexible and dynamic approach to UI rendering.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708965148899/8700f1a2-0f23-433b-bce8-d7f8d2cf2b31.jpeg align="center")

In the realm of server-driven UI, the server's response takes the form of proprietary markup comprehensible to the app. Rather than merely fetching a list of products, the app requests a comprehensive list view. This list view, in turn, comprises a series of row views, each meticulously defined with text and image views. The server's markup encapsulates details about spacing, alignment, colour, and typography, essentially encapsulating the entire blueprint for the UI elements. This consolidated approach not only streamlines the communication between the app and server but also empowers the server to dictate the intricate details of UI presentation.

```json
{
  "list": {
    "rowHeight": 44,
    "dividerColor": "#979797",
    "rows": [
      {
        "padding": [7, 14, 7, 14],
        "image": {
          "source": "https://images.example.com/instinct.jpg",
          "alignment": "leading",
          "width": 30,
          "height": 30
        },
        "label": {
          "text": "Rocky Mountain Instinct",
          "alignment": "top",
          "fontSize": 11,
          "fontWeight": "semibold",
          "color": "#000000"
        },
        //...
      },
      //...
    ]
  }
}
```

The app renders the response from the server and the result is identical to the version using traditional development techniques.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708965303845/0c395d15-8941-41fd-b0d5-ece4eb4755e6.jpeg align="center")

Does this sound familiar? This is exactly how web browsers work with HTML and CSS. Remember, everything old is new again.

## **Unveiling the Enchantment: Advantages of Server-Driven UI**

The true benefits of server-driven UI (SDUI) become evident when considering the efficiency of making changes. In the traditional development approach, the UI iterations necessitate a time-consuming release cycle, involving multiple steps:

1. Developers write code to make the desired UI changes.
    
2. The UI changes are reviewed by testers.
    
3. A new version of the app is submitted to the App/Play Store.
    
4. Apple/Google reviews and approves it.
    
5. Users update to the new version.
    

Contrastingly, with server-driven UI, the initial step is replaced with a straightforward server-side update to the listing screen markup. No new code is written, eliminating the need for testing. Since there's no modification to the app itself, there's no requirement to submit a new version, bypassing the wait for approval from Apple or Google. As a result, users witness the changes immediately, as there's no delay associated with updating the app.

In essence, the updates that previously consumed weeks or months in the traditional approach can now be executed in a matter of days or even hours with server-driven UI. This streamlined process ensures consistent changes across both iOS and Android apps, with all users experiencing the updated version simultaneously. The accelerated deployment of changes is a key advantage of adopting server-driven UI.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1708965529391/dedbccdd-33ad-49ec-92dd-8dd8b20ee3f5.jpeg align="center")

## **Two-Phase Rendering**

In the server-driven UI (SDUI) example we explored earlier, the UI and data were combined in a single server response. However, one drawback of this approach is that the user interface must be fetched each time the listing screen is accessed. This leads to a momentary display of a blank screen along with a loading indicator while awaiting the UI and data from the server. This can be perceived as a regression from the traditional method where the UI is embedded in the app, eliminating the need for users to wait for it to load.

An alternative SDUI implementation, as exemplified by Judo, involves a two-phase approach by separating the retrieval of the user interface and data. This not only significantly reduces server response sizes for list views but also enables the pre-fetching of the user interface. In this method, the UI can be fetched in advance and stored locally on the device, ensuring it is readily available before the user initiates the view. Moreover, the UI fetching process can be conducted in the background, even while the user's phone is in their pocket, maintaining its currency at all times.

When the user opens the app and accesses the listing screen, the pre-fetched UI is presented instantaneously. Subsequently, the data is fetched from the server, seamlessly combined with the pre-fetched UI, and transformed into the list view. This innovative approach strikes a balance, delivering a user experience indistinguishable from traditionally developed apps while providing greater control over the timing and execution of UI updates.

## Conclusion

The evolution from traditional app development to the innovative realm of server-driven UI (SDUI) marks a transformative shift in how we approach user interface updates. The conventional methods, laden with lengthy release cycles, platform-specific challenges, and delayed user access, have been effectively challenged by SDUI. By centralizing control and separating UI and data retrieval, SDUI not only streamlines the update process but also empowers developers to make changes swiftly and consistently across iOS and Android platforms. The dynamic capabilities of SDUI, particularly when adopting a two-phase approach, allow for pre-fetching UI, resulting in an app experience that is both seamless and responsive. With these advancements, we find ourselves at the intersection of efficiency and user satisfaction, poised to embrace a future where UI updates are not just imperative but instantaneous, ensuring our apps remain agile and adaptable in the ever-evolving landscape of technology.