---
layout: post
title: xHTML A basic Form
---

How to make a basic form to submit anything to your JavaBean Class.

## Task Description

I am going to show how to make a basic form to submit things to your JavaBean Class. This is very useful because it makes it very easy to transfer information and work with it.

**Goals**

1. Show an easy example of a form and explain it in detail.


## Work

This is a task we did in our lessons. It is about a character customizer, where we can change the color of the hair, eye and more. This form will result in a normal form with a textBox and a submitButton.

```xml
<h:form id="eyeColor-form">
            <h:outputLabel for="eyeColor"></h:outputLabel>
            <h:inputText id="eyeColor" value="#{characterBean.eyeColor}" required="true" requiredMessage="Eye"></h:inputText>
            <h:commandButton id="submit-button" value="Submit" action="skinColorSelector.xhtml"></h:commandButton>
</h:form>
```

![image](https://user-images.githubusercontent.com/86788562/131391923-f0adf18b-7a8c-45cd-9be7-74dbc7be21a9.png)

The `<h:inputText>` of the form is for textBox that is showing. The `value="#{characterBean.eyeColor}"` defines the place where the value/text will be submitted to.

```xml
<h:inputText id="eyeColor" value="#{characterBean.eyeColor}" required="true" requiredMessage="Eye"></h:inputText>
```

The `<h:commandButton>` is the button that is showing. The `value="Submit"` is for the type of the button and the `action="skinColorSelector.xhtml"` stands for the next page that will be opened. The action part can also be directed to a java file which makes pages dynamic.

```xml
<h:commandButton id="submit-button" value="Submit" action="skinColorSelector.xhtml"></h:commandButton>
```


## Reflection

I have problem with concentrating in this modul, because I often do some IT stuff but not the tasks I should be doing. I'll try to focus more in the following lessons by strictly following the daily schedule and try to isolate other distractions.

**Goals verification**
1. I explained the whole form I showed. You should now be able to make a basic form by yourself.



