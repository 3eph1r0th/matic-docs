---
id: meta-transactions
title: Meta লেনদেন
sidebar_label: Overview
description: Meta লেনদেন এবং আপনি কীভাবে সেগুলো ব্যবহার করতে পারেন সে সম্পর্কে জানুন।
keywords:
  - docs
  - polygon
  - matic
  - transactions
  - meta transactions
  - gasless
image: https://matic.network/banners/matic-network-16x9.png
slug: meta-transactions
---

দৈনিক স্মার্ট চুক্তির কল তাদের সর্বোচ্চ পর্যায়ে থাকে, যা প্রতিদিন প্রায় 2.5 থেকে 3 মিলিয়ন হয়ে থাকে। DApps তাদের উপযোগিতা বুঝতে শুরু করেছে, তবে নিজেদের বা অন্যদের সফলতার কারণে শিকারে পরিণত হচ্ছে। গ্যাস ফিয়ের কারণে। বলা বাহুল্য, ব্যবহারকারীদের অন্তর্ভুক্ত করার ক্ষেত্রে বর্তমান সমস্যা এবং বর্তমান UX-এর চ্যালেঞ্জ দূর করা সহজ কাজ নয়।

## স্মার্ট চুক্তি মেরামত করা {#servicing-smart-contracts}

ডিজাইন অনুযায়ী, স্মার্ট চুক্তি হলো ডিটার্মিনিস্টিক স্টেট মেশিন, যা তখনই সম্পন্ন হয় যখন লেনদেনের ফি নেটওয়ার্কের হিসেব করার সম্পদগুলো ব্যবহার করে চুক্তির লজিকগুলো মেরামত করার জন্য প্রদান করা। এটি Ethereum (এবং Polygon)-এ একটি গ্যাস-মিটারযুক্ত মডেল দ্বারা সম্পন্ন হয়।

## লেনদেন করার বর্তমান অবস্থা {#the-current-state-of-transacting}

Ethereum (এবং অনুরূপ অন্যান্য ব্লকচেইনে) এই প্রচলিত লেনদেনের মডেলটির সীমাবদ্ধতা রয়েছে। একটি সাধারণ সীমাবদ্ধতা হলো, গ্যাসের অর্থ পরিশোধ করার জন্য ব্যবহারকারীর কোনো উপায় না থাকা। ডিফল্টরূপে, লেনদেনের প্রেরক পরিশোধকারী হিসেবে কাজ করেন, কারণ এই আচরণগুলো পরস্পর যুক্ত, তাই যদি কোনো ব্যবহারকারী কোনো লেনদেন তৈরি ও প্রেরণ করার চেষ্টা করেন, তবে তারা সংশ্লিষ্ট গ্যাসের ফি-এর জন্য দায়বদ্ধ। অনুরূপভাবে, যদি কোনো ব্যবহারকারী কোনো dApp তৈরি করেন, এর সাথে ইন্টারেক্ট করেন বা তা রান করেন, তবে তাকে গ্যাসের অর্থ প্রদান করতে হবে।

গড়পড়তা একজন ব্যবহারকারী crypto ক্রয় করবেন এবং অ্যাপ্লিকেশনের সাথে ইন্টারঅ্যাক্ট করতে গ্যাসের জন্য অর্থ প্রদান করবেন বলে প্রত্যাশা করা অবাস্তব। এটি মোকাবেলা করার জন্য যা করা যেতে পারে তা হলো কোনো লেনদেনের প্রেরককে একজন প্রদানকারী হিসেবে কাজ করা থেকে বিচ্ছিন্ন করার জন্য, লেনদেন সম্পন্ন করা বৃদ্ধি করার এবং নির্ঝঞ্ঝাট লেনদেনের অভিজ্ঞতা শুরু করার জন্য সুযোগ সক্রিয় করা।

গ্যাস তদারকি করার জন্য, সরাসরি লেনদেন নির্বাহ করার পরিবর্তে একটি মিডলওয়ার থাকতে পারে (একটি তৃতীয় পক্ষের মাধ্যমে)। এক্ষেত্রে Meta লেনদেন প্রাসঙ্গিক হয়ে ওঠে।

## Meta লেনদেন কী? {#what-are-meta-transactions}

Meta লেনদেনের মাধ্যমে যে কোনো ব্যক্তি ব্লকচেইনের সাথে ইন্টারঅ্যাক্ট করতে পারবেন। সেগুলোর জন্য ব্যবহারকারীদের লেনদেনের ফিয়ের মাধ্যমে নেটওয়ার্কের পরিষেবার জন্য পেমেন্ট করতে টোকেনের প্রয়োজন নেই। এটি সম্পন্ন করা সম্ভব কোনো লেনদেনের প্রেরক এবং গ্যাস ফি প্রদানকারীকে আলাদা করার মাধ্যমে।

একটি সমাধান যা নতুন ব্যবহারকারীকে যুক্ত করতে এবং বর্তমান ব্যবহারকারীদেরকে সাহায্য করতে পারে।

কোনো লেনদেন নির্বাহকারী একজন প্রেরক হিসেবে কাজ করে। গ্যাস ব্যয় করার পরিবর্তে, তারা শুধুমাত্র একটি লেনদেনের অনুরোধ তৈরি করে, তাদের প্রাইভেট কী-এর মাধ্যমে তাদের কাঙ্ক্ষিত কাজটি স্বাক্ষর করার মাধ্যমে (লেনদেনের প্যারামিটার)। Meta লেনদেন হলো একটি নিয়মিত Ethereum লেনদেন অতিরিক্ত প্যারামিটার অন্তর্ভুক্ত করে Meta লেনদেন গঠনের জন্য।

স্বাক্ষরিত লেনদেনের প্যারামিটারগুলো একটি সেকেন্ডারি নেটওয়ার্কে পাস হয়, যা একটি রিলেয়ার হিসেবে কাজ করে। যদিও এর জন্য বিভিন্ন স্কিম রয়েছে, তবে রিলেয়ারগুলো সাধারণভাবে কোন লেনদেনগুলো জমা দেওয়া মূল্যবান তা নির্বাচন করে লেনদেনটি যাচাই করার মাধ্যমে (যেমন dApp-এর সাথে সম্পর্কিত হওয়ার মাধ্যমে)। যাচাই করার পরে, রিলেয়ার অনুরোধটিকে (স্বাক্ষরিত বার্তা) একটি প্রকৃত লেনদেনে মোড়াবে (যার অর্থ গ্যাস ফি প্রদান করা) এবং একে নেটওয়ার্কে সম্প্রচার করে, যেখানে চুক্তিটি আসল স্বাক্ষর যাচার করার মাধ্যমে লেনদেনের মোড়ক খুলে এবং ব্যবহারকারীর পক্ষে এটি পরিচালনা করে।

:::note Meta এবং ব্যাচ শব্দ দুটি কারো কাছে সদৃশ মনে হতে পারে

স্পষ্ট করার জন্য: Meta লেনদেন একটি ব্যাচ লেনদেন থেকে ভিন্ন, যেখানে একটি ব্যাচ লেনদেন হলো এমন একটি লেনদেন যা একবারে একাধিক লেনদেন পাঠাতে পারে এবং তারপর একটি একক প্রেরক থেকে ক্রমান্বয়ে সম্পন্ন করতে পারে (একক নির্দিষ্ট সময়)।

:::

সংক্ষেপে, Meta লেনদেন হলো একটি ডিজাইন প্যাটার্ন যেখানে:

* একজন ব্যবহারকারী (প্রেরক) তাদের প্রাইভেট কী দিয়ে একটি অনুরোধ স্বাক্ষর করে এবং এটি একটি রিলেয়ারের কাছে পাঠায়
* রিলেয়ার অনুরোধটিকে একটি tx-এ র‍্যাপ করে এবং এটি একটি চুক্তিতে পাঠায়
* চুক্তি tx আনর‍্যাপ করে এবং এটি নির্বাহ করে

নেটিভ লেনদেন বলতে বোঝায় যে "প্রেরক" "প্রদানকারী"ও। যখন "প্রদানকারী"-কে "প্রেরক", থেকে দূরে নেওয়া হয়, তখন "প্রেরক" আরো বেশি "ইন্টেন্ডার" হয় - প্রেরক লেনদেনের উদ্দেশ্য প্রদর্শন করে যা তারা ব্লকচেইনে সম্পন্ন করতে চাইতে পারে, তাদের মেসেজ সম্পর্কিত সুনির্দিষ্ট প্যারামিটার ধারণকারী একটি মেসেজ স্বাক্ষর করে এবং সম্পূর্ণরূপে তৈরি কোনো লেনদেন নয়।

## ব্যবহারের ঘটনা {#use-cases}

স্মার্ট চুক্তি সহ dApps এবং ইন্টারেকশন স্কেল করার জন্য কেউ Meta লেনদেনের ক্ষমতা কল্পনা করতে পারেন। একজন ব্যবহারকারী শুধুমাত্র একটি গ্যাসহীন লেনদেনই তৈরি করতে পারেন না, বরং তারা অনেক সময় এবং একটি অটোমেশন টুল দিয়েও করতে পারেন Meta লেনদেন বাস্তবিক ব্যবহারের ক্ষেত্রে পরবর্তী অ্যাপ্লিকেশনের প্রবাহকে প্রভাবিত করতে পারে। Meta লেনদেন স্মার্ট চুক্তিr লজিকে বাস্তব ইউটিলিটি সক্ষম করে, যা প্রায়ই গ্যাস ফি এবং অন-চেইনে প্রয়োজনীয় ইন্টারেকশনের জন্য সীমিত।

### ভোট দেওয়ার মাধ্যমে উদাহরণ {#example-with-voting}

একজন ব্যবহারকারী অন-চেইন পরিচালনায় অংশগ্রহণ করতে চান এবং তারা একটি ভোটিং চুক্তির মাধ্যমে কোনো একটি বিশেষ ফলাফলের জন্য ভোট দিতে চান। ব্যবহারকারী একটি বার্তা স্বাক্ষর করবে, যা এই বিশেষ চুক্তিতে একটি ভোটে ব্যবহারকারীর সিদ্ধান্ত বর্ণনা করে। প্রচলিতভাবে, চুক্তির সাথে ইন্টারঅ্যাক্ট করার জন্য তাদেরকে একটি গ্যাস ফি দিতে হবে (এবং কীভাবে চুক্তির সাথে ইন্টারঅ্যাক্ট করতে হয় তা জানতে হবে), কিন্তু তার পরিবর্তে, তারা তাদের ভোটের জন্য প্রয়োজনীয় তথ্য সহ তারা একটি Meta লেনদেন (অফ-চেইন) স্বাক্ষর করতে পারেন এবং এটি একটি রিলেয়ারে পাস করে, যা তাদের পক্ষে লেনদেনটি নির্বাহ করবে।

স্বাক্ষরিত মেসেজটি একটি রিলেয়ারে পাঠানো হয় (ভোটদানের তথ্য সম্পর্কে স্বাক্ষরিত tx প্যারাম)। রিলেয়ার যাচাই করে যে, এই লেনদেনটি একটি অগ্রাধিকার ভোট, ভোটদানের অনুরোধটিকে একটি প্রকৃত লেনদেনে পরিণত করে,
গ্যাস ফি প্রদান করে, এবং ভোটদানের চুক্তিতে এটি সম্প্রচার করে। ভোটদানের চুক্তির দিকে সবকিছু পরীক্ষা করা হয় এবং ব্যবহারকারীর পক্ষে ভোট প্রদান করে।

## সেগুলো ব্যবহার করে দেখুন {#try-them-out}

বিভিন্ন পদ্ধতির সাথে আপনার পরিচিতির বিষয়টি ধরে নিয়ে, আপনি Meta লেনদেন আপনার dApp-এ সংহত করতে পারেন এবং আপনি Meta লেনদেনে মাইগ্রেট করছেন কি না বা এটি ব্যবহার করে নতুন কোনো dApp তৈরি করছেন কি না তার উপর নির্ভর করে।

Polygon-এ Meta লেনদেন সহ আপনার dApp ইন্টিগ্রেট করতে, আপনি নিম্নলিখিত একটি রিলেয়ার বেছে নিতে পারেন বা একটি কাস্টম সমাধান স্পিন করতে পারেন:

* [Biconomy](https://docs.biconomy.io/products/enable-gasless-transactions)
* [গ্যাস স্টেশন নেটওয়ার্ক (GSN)](https://docs.opengsn.org/#ethereum-gas-station-network-gsn)
* [Infura](https://infura.io/product/ethereum/transactions-itx)
* [Gelato](https://docs.gelato.network/developer-products/gelato-relay-sdk)
