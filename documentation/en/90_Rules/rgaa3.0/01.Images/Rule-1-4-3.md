# RGAA 3.0 -  Rule 1.4.3

## Summary

This test consists in detecting captcha form buttons and thus defining the applicability of the test.

Human check will be then needed to determine whether the alternative is pertinent.

## Business description

### Criterion

[1.4](http://disic.github.io/rgaa_referentiel_en/RGAA3.0_Criteria_English_version_v1.html#crit-1-4)

###Test

[1.4.3](http://disic.github.io/rgaa_referentiel_en/RGAA3.0_Criteria_English_version_v1.html#test-1-4-3)

### Description
For each button associated
    with an image (<code>input</code> tag with the attribute
    <code>type="image"</code>), used as a CAPTCHA or test image, with an
    <code>alt</code> attribute, meet the following conditions?
    <ul><li>The content of the <code>alt</code> attribute describes the nature and purpose of the image </li>
  <li>If present, the value of the <code>title</code> attribute
   matches the value of the <code>alt</code> attribute</li>
    </ul> 


### Level

**A**

## Technical description

### Scope

**Page**

### Decision level

**Semi-Decidable**

## Algorithm

### Selection

##### Set1

All the `<input>` tags with the "type" attribute equals to "image" and an `"alt"` attribute (css selector : `input[alt][type=image]`)

#### Set2

All the elements of **Set1** identified as a CAPTCHA (see Notes for details about CAPTCHA characterisation).

### Process

#### Test1

For each element of **Set2**, raise a MessageA

##### MessageA : Check captcha alternative

-    code : **CheckCaptchaAlternative** 
-    status: Pre-Qualified
-    parameter : `"alt"` attribute, `"src"` attribute, tag name, snippet
-    present in source : yes

### Analysis

#### Not Applicable

The page has no `<input>` tag with an `"type"` attribute equals to "image" and an `"alt"` attribute identified as a captcha (**Set2** is empty)

#### Pre-qualified

In all other cases

## Notes

### Captcha detection

An element is identified as a CAPTCHA when the "captcha" occurrence is found :

- on one attribute of the element
- or within the text of the element
- or on one attribute of one parent of the element
- or within the text of one parent of the element
- or on one attribute of a sibling of the element
- or within the text of a sibling of the element



##  TestCases 

[TestCases files for rule 1.4.3](https://github.com/Asqatasun/Asqatasun/tree/master/rules/rules-rgaa3.0/src/test/resources/testcases/rgaa30/Rgaa30Rule010403/) 


