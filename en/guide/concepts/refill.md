# {% if locale == "en-com" %}Topping up your account{% endif %}

## Deposit methods {#method}

You can use the following options to add funds to your Toloka account:

#### Visa or EuroCard/MasterCard.

The payment is completed within 15 minutes.

If you chose {% if locale == "en-com" %}**Profile type → Legal entity**{% endif %} when [registering](access.md) in Toloka, you must use a corporate bank card.

{% cut "List of countries where bank card transfers are available" %}

{% if locale == "en-com" %}

- Russia
- Ukraine
- Belarus
- Kazakhstan
- Uzbekistan
- Turkey
- Åland Islands
- Albania
- Andorra
- Armenia
- Austria
- Azerbaijan
- Belgium
- Bosnia and Herzegovina
- Bulgaria
- Canada
- China
- Croatia
- Cyprus
- Czech Republic
- Denmark
- Estonia
- Faroe Islands
- Finland
- France
- Georgia
- Germany
- Gibraltar
- Greece
- Guernsey
- Hong Kong
- Hungary
- Iceland
- Ireland
- Isle of Man
- Israel
- Italy
- Jersey
- Kyrgyzstan
- Latvia
- Liechtenstein
- Lithuania
- Luxembourg
- Macedonia
- Malaysia
- Malta
- Moldova
- Monaco
- Montenegro
- Netherlands
- Norway
- Poland
- Portugal
- Romania
- San Marino
- Serbia
- Slovakia
- Slovenia
- South Korea
- Spain
- Svalbard and Jan Mayen
- Sweden
- Switzerland
- Taiwan
- Tajikistan
- Thailand
- Turkmenistan
- United Arab Emirates
- United Kingdom
- USA
- Vatican City State
- Vietnam

{% endif %}

{% endcut %}

#### Bank transfer

The money transfer takes from 3 to 10 days.

When making a transfer, specify the invoice number in the payment reference.

#### PayPal transfer

The payment is completed within 15 minutes.

You will be redirected to the [PayPal]({{ paypal }}) site to complete the payment.

{% note alert "Restriction" %}

PayPal transfer isn't available for Swiss residents.

{% endnote %}

{% cut "Regions where PayPal transfer is not allowed" %}

- Crimea
- Ukraine
- Uzbekistan
- Turkey
- Iran
- Cuba
- Sudan
- Syria
- North Korea

The full list can be found on the site of the [USA Department of the Treasury](https://www.treasury.gov/resource-center/sanctions/Programs/Pages/Programs.aspx).

{% endcut %}

## Step-by-step instructions {#step-by-step}

1. On the [Profile]({{ profile }}) page, click {% if locale == "en-com" %}**Top up account**{% endif %}.

1. If you're topping up your account for the first time, the {% if locale == "en-com" %}**Connect to billing system**{% endif %} page will open. Follow these steps:

    1. Fill in your details.

        {% note info %}

        This information will be included in accounting documents (service invoices).

        {% endnote %}

    1. Click {% if locale == "en-com" %}**Connect**{% endif %}.

1. Enter the transfer amount.

    The maximum top-up amount from a bank card is $3500.

1. Choose the payment method: {% if locale == "en-com" %}**Bank card**{% endif %} or {% if locale == "en-com" %}**Bank transfer or Paypal**{% endif %}.

1. Click {% if locale == "en-com" %}**Top up**{% endif %}.

    {% list tabs %}

    - Сard

      1. Enter your card details.

          {% note info %}

          To avoid having to enter your card details again later, enable the {% if locale == "en-com" %}**Save card for future payments**{% endif %} option.

          {% endnote %}

      1. Click the {% if locale == "en-com" %}**Pay**{% endif %} button.

      1. Track the receipt of money in your Toloka account on the [Profile]({{ profile }}) page (the {% if locale == "en-com" %}**Transactions history**{% endif %} tab).

    - Bank account/PayPal

      1. You will be redirected to the [Yandex.Balance]({{ balance }}) service.

      1. Select the payer (individual or legal entity) and the desired payment method.

      1. Attach the documents:

          - For individuals

            - A copy of the photo page of your passport.

          - For legal entities

            - A certificate of incorporation.

            - A business card with bank details and contact information.

      1. Click the {% if locale == "en-com" %}**Select**{% endif %} button.

      1. Check the data you entered.

          To return to choosing a payment method and changing the payer's details, click {% if locale == "en-com" %}**Change payer or payment method**{% endif %}.

      1. Click the {% if locale == "en-com" %}**Create a billing invoice**{% endif %} button.

          If you chose {% if locale == "en-com" %}**Payment method → Bank deposit in US dollars for non-resident individuals (Switzerland)**{% endif %}, you will receive an invoice with payment details.

      1. Click the {% if locale == "en-com" %}**Pay**{% endif %} button.

          If you chose {% if locale == "en-com" %}**Payment method → PayPal**{% endif %}, you will be redirected to the PayPal site for payment.

          If you chose {% if locale == "en-com" %}**Payment method → Banking card in dollars — non residents Switzerland) — US dollars**{% endif %}, enter your bank card information and complete the payment. The money will be converted at your bank's rate if the card currency is not dollars.

          {% note info %}

          If you use a  wallet, you may be asked to enter the [payment password](https://yandex.ru/support/money/password/permanent.html) when you go to payment.

          {% endnote %}

      1. Track the money transfer:

        - On the Toloka [Profile]({{ profile }}) page (the {% if locale == "en-com" %}**Transactions history**{% endif %} tab).

        - In Yandex.Balance (the [Invoices]({{ invoices }}) page).

    {% endlist %}

## What's next {#what_next}

- [Start the pool](pool-run-and-stop.md).

## Troubleshooting {#troubleshooting}

[Get closing documents and invoices](../troubleshooting/support.md#feedback_g3b_vj3_qjb)

[Refund money transferred to the Toloka account](../troubleshooting/support.md#feedback_khw_wc3_qjb)

If the money wasn't credited to the account within the specified period:

{% include [contact-support](../_includes/contact-support.md) %}