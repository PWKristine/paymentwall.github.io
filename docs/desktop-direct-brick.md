---
id: desktop-direct-brick
title: Brick
sectionid: docs
permalink: direct/brick-home
---
# Brick

<div id="payment-form-container">
</div>
<script src="https://api.paymentwall.com/brick/brick.1.4.js"></script>
<script type="text/javascript">
	var brick = new Brick({
		public_key: 't_a93db6bffafdda5c57ab48296fdbba',
		amount: 0.99,
		currency: 'USD',
		container: 'payment-form-container',
		action: 'http://testbed1.stuffio.com/bricktest/brick-doc.php',
		form: {
			merchant: 'Your store',
			product: 'Your goods name',
			pay_button: 'Pay',
			zip: true
		}
	});

	brick.showPaymentForm(function(data) {

	}, function(errors) {
    // handle errors
	});
</script>

Brick is a pure credit card payment solution provided by Paymentwall. It allows you to develop your own payment experience, specifically for credit cards payments.

It can be used in [Paylet](/paylet-home) as a credit card gateway or you can also integrate it using [Brick API](/apis#section-brick-onetime_token) in your application. 

## Try with Brick

You can do a test payment by using Brick test cards available in [Sandbox](/direct/brick/sandbox) or the card information:

* Card number: 4242 4242 4242 4242.

* Expiry date: 03/21.

* CVV: 097.

* Email: test@paymentwall.com.

Each successful payment has a one-time token which will be used in further charge request.

## Components

* [Create a form](/direct/brick/create-form) to collect payment details and generate a one-time token. 

* Perform request according to your product type: [onetime payment](/direct/brick/charge) or [subscription](/direct/brick/subscription).

## Requirements

* Your payment pages must be loaded via **HTTPS**.

* [3D Secure](http://www.mastercard.com/gateway/implementation_guides/3D-Secure.html) ([verified by Visa](https://www.visaeurope.com/making-payments/verified-by-visa/)) should be implemented into your payment system. See how to [apply 3D Secure](/direct/brick/3dSecure) in Brick.

* A Paymentwall project which is using the the Digital Goods API.

## Use Brick

Once you have created a Paymentwall project, you need to:

+ Get your project credentails, click the Brick logo on your project and you will find a project and secret key provided by Paymentwall:
	- Brick Test Keys. A random 32-bit string starting with the prefix ```t_``` which is used in the sandbox environment for payment flow verification.
	- Brick Live Keys. A random 32-bit string which is used to collect payments from your customers. To obtain the Live keys, your project needs to be reviewed by our team.

* Integrate Brick components in your system. See [components](#components) for more details.

* Setup Pingback listener

	- [Pingback](/default-pingback) is Paymentwall's instant payment notification. Each pingback has a unique reference ID in our system. Kindly store it and proceed with the delivery according to our pingback request.



