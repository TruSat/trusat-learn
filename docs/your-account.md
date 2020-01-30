---
id: your-account
title: Your account
sidebar_label: Your account
---

## What is the secret that was emailed to me when I created an account?

In TruSat the identity of users is verified by a unique address found in their Ethereum wallet. You can see your address by hovering over your name in your profile page. When you sign up with an email and password, the following process happens under the hood:

- An Ethereum wallet is created for you in your browser (TruSat never has access to your wallet)
- The wallet is then encrypted with the password you provided to create a unique "Secret"
- This secret is emailed to you

In future when you need to sign in again you must verify that you are the owner of the Ethereum address tied to your identity by providing two things:

- The secret
- The password (now used to decrypt your wallet)

Therefore it is vital that you take care to store your secret and password somewhere safe. If you wish to protect your identity (wallet) in a more secure way, perhaps you can consider the browser plugin [MetaMask](https://metamask.io/). See your settings page for a handy guide on how to migrate away from the email/password/secret login flow to a more streamlined and secure one-click login via MetaMask.
