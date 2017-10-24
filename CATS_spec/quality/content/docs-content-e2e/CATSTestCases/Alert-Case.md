# Alert Cases
This case is to verify if there are any alerts(Contain: Note, Impotent, Tip, Warning, Caution) with empty content.
This test cases covered hub page,conceptual page,reference namespace page and reference class type page and total 1 cases currently.

**Below is test cases list:**
* [Missing alerts](#missing-alerts)

## <a id='missing-alerts'></a>Missing alerts
### Check point
* Check if there are any missing alerts

**Steps**
1. Open the test URL one by one.
2. If there are alert tag (Note/Impotent/Tip/Warning/Caution) on page, check if any alert with empty content.

**Expected behavior**
* All the alert (Note/Impotent/Tip/Warning/Caution) have content

## Alert testing
> [!NOTE]
> **Custom policies are in public preview.**

> [Custom policies](..\articles\active-directory-b2c\active-directory-b2c-overview-custom.md#custom-policies) are designed primarily for identity pros who need to address complex scenarios. For most scenarios, we recommend that you use Azure Active Directory B2C [built-in policies](..\articles\active-directory-b2c\active-directory-b2c-overview-custom.md). Built-in policies are easier to set up for your configuration. You can use built-in and custom policies in the same Azure Active Directory B2C tenant. To learn more, see the [overview of custom policies](..\articles\active-directory-b2c\active-directory-b2c-overview-custom.md).
