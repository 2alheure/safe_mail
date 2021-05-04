# A Vue.js component to safely print your email on your website

- [A Vue.js component to safely print your email on your website](#a-vuejs-component-to-safely-print-your-email-on-your-website)
  - [Description](#description)
    - [And then it begins...](#and-then-it-begins)
    - [Do not just delete it](#do-not-just-delete-it)
  - [This component](#this-component)
  - [Usage](#usage)

## Description
We all know this kind of situation: you have a landing page, allowing people to send you a contact message at the bottom of the page.  
To do so, you made a nice form, and for accessibility purpose, you also add a link with your email address next to it.

### And then it begins...
Dozens, if not hundreds of mails! You're happy, you're telling youself "It's the begining of my fortune! I have plenty of people wanting to chat with me! I'm so happy".  
But it turns out that on 100 emails you've got, 99 are from spam bots which read your email address and sold it.

### Do not just delete it
Stop undergoing this!  
There are plenty of tips allowing you to display an email address *relatively safely*.  
  
The main point is, not to allow bots to get your email address as is. So people add scripts that encrypt their addresses. But bots do read the HTML generated.  
So if you simply write `<a htref="mailto:{encryptedmail}">clear@mail.com</a>`... It's not good enough.

## This component
This components hides your email address in both the `<a>` tag **AND** its `href`.  
Just give it a try, it'll change your life... Or at least your box's one.^^'

## Usage
Run `npm install @2alheure/vue-safe-mail`. Import it. Use it.  
It's as simple as that! =D

```js
<SafeMail :email="email" :title="title" />

<script>
import SafeMail from "@2alheure/vue-safe-mail";

export default {
  components: {
    DataTable
  },
  data() {
    return {
      email: "my.address@email.com",
      title: "Click here to send me a nice message which is not spam!"
    }
  }
};
</script>
```

It renders a `<a>` tag with a `href` attribute pointing to the given email... but protected against bots harvest. =P
