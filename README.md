# Bing Image Selector Custom Element for Kentico Kontent

This is a [custom element](https://docs.kontent.ai/tutorials/develop-apps/integrate/integrating-your-own-content-editing-features) for [Kentico Kontent](https://kontent.ai) that allows users to search Bing images and select one. **NOTE: Selected image may be subject to copyright and/or usage restrictions.**

![Screenshot of custom element](BingImageSelector.gif)

## Setup

1. Create a [Cognitive Services API account](https://docs.microsoft.com/azure/cognitive-services/cognitive-services-apis-create-account) with access to the Bing Search APIs. If you don't have an Azure subscription, you can [create an account](https://azure.microsoft.com/try/cognitive-services/?api=bing-web-search-api) for free.
1. Deploy the code to a secure public host
   - See [deploying section](#Deploying) for a really quick option
1. Follow the instructions in the [Kentico Kontent documentation](https://docs.kontent.ai/tutorials/develop-apps/integrate/integrating-your-own-content-editing-features#a-3--displaying-a-custom-element-in-kentico-kontent) to add the element to a content model.
   - The `Hosted code URL` is where you deployed to in step 1
   - Pass the necessary parameters as directed in the [JSON Parameters configuration](#json-parameters) seciton of this readme.

## JSON Parameters

The custom element requires an API key (`apikey`) for the [Bing Search APIs](https://azure.microsoft.com/en-us/try/cognitive-services/). All other parameters are optional:

```Json
{
  "apikey": "YOUR_GOOGLE_API_KEY",
  "count": 10,
  "offset": 0,
  "mkt": "en-US",
  "safeSearch": "Off"
}
```

`count` (optional) - The number of image results to return in the response. The actual number delivered may be less than requested.

`offset` (optional) - The zero-based offset that indicates the number of image results to skip before returning results.

`mkt` (optional) - The market where the results come from. Typically, this is the country where the user is making the request from; however, it could be a different country if the user is not located in a country where Bing delivers results. The market must be in the form -. For example, en-US. Supported markets are: es-AR,en-AU,de-AT,nl-BE,fr-BE,pt-BR,en-CA,fr-CA,es-CL,da-DK,fi-FI,fr-FR,de-DE,zh-HK,en-IN,en-ID,en-IE,it-IT,ja-JP,ko-KR,en-MY,es-MX,nl-NL,en-NZ,no-NO,zh-CN,pl-PL,pt-PT,en-PH,ru-RU,ar-SA,en-ZA,es-ES,sv-SE,fr-CH,de-CH,zh-TW,tr-TR,en-GB,en-US,es-US

`safeSearch` (optional) - A filter used to filter results for adult content. Options are "Off", "Moderate" or "Strict".

## Deploying

Netlify has made this easy. If you click the deploy button below, it will guide you through the process of deploying it to Netlify and leave you with a copy of the repository in your GitHub account as well.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/Kentico/kontent-custom-element-bing-image-selector)

## What is Saved?

A string containing the image's URL.

## Contributors

Originally contributed by: [@maartenvdh](https://github.com/maartenvdh)
