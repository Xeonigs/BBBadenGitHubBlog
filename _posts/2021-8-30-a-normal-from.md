---
layout: post
title: "xHTML: A normal Form"
---

How to make a normal form to submit anything to your JavaBean Class.

## Task Description

I am going to show how to make a normal form to submit things to your JavaBean Class. This is very useful because it makes it very easy to transfer information and work with it.



**Goals**

- Show an easy example of a form and explain it in detail.



## Work

This is a task we did in our lessons. It is about a character customizer, where we can change the color of the hair, eye and more. This form will result in a normal form with a textBox and a submitButton.

```xhtml
<h:form id="eyeColor-form">
            <h:outputLabel for="eyeColor"></h:outputLabel>
            <h:inputText id="eyeColor" value="#{characterBean.eyeColor}" required="true" 									requiredMessage="Eye"></h:inputText>
            <h:commandButton id="submit-button" value="Submit" action="skinColorSelector.xhtml">	
    		</h:commandButton>
</h:form>
```

<<PICTURE>>



The `<h:inputText>` of the form is for textBox that is showing. The `value="#{characterBean.eyeColor}"` defines the place where the value/text will be submitted to.

```xhtml
<h:inputText id="eyeColor" value="#{characterBean.eyeColor}" required="true" requiredMessage="Eye"></h:inputText>
```



The `<h:commandButton>` is the button that is showing. The `value="Submit"` is for the type of the button and the `action="skinColorSelector.xhtml"` stands for the next page that will be opened. The action part can also be directed to a java file which makes pages dynamic.

```xhtml
<h:commandButton id="submit-button" value="Submit" action="skinColorSelector.xhtml"></h:commandButton>
```



## Reflection

The 
