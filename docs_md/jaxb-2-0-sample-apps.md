Sample Apps {#jaxb-2-0-sample-apps}
===========

This page summarizes basic use-cases for Java-2-Schema, Schema-2-Java,
and lists all of the sample applications that ship with JAXB.

Using the Runtime Binding Framework {#section-3589085759105448}
-----------------------------------

### Schema-2-Java {#section-527832527889161}

Schema-2-Java is the process of compiling one or more schema files into
generated Java classes. Here are some of the basic steps for developing
an app:

1.  Develop/locate your schema

2.  Annotate the schema with binding customizations if necessary (or
    place them in an external bindings file)

3.  Compile the schema with the XJC binding compiler

4.  Develop your JAXB client application using the Java content classes
    generated by the XJC binding compiler along with the
    `javax.xml.bind` runtime framework

5.  Set your `CLASSPATH` to include all of the [???](#jars)

6.  Compile all of your Java sources with `javac`

7.  Run it!

### Java-2-Schema {#section-308004238994006}

Java-2-Schema is the process of augmenting existing Java classes with
the annotations defined in the `javax.xml.bind.annotation` package so
that the JAXB runtime binding framework is capable of performing the
(un)marshal operations. Here are the basic steps for developing an app:

1.  Develop your data model in Java

2.  Apply the `javax.xml.bind.annotation` annotations to control the
    binding process

3.  Set your `CLASSPATH` to include all of the [???](#jars)

4.  Compile your data model with `javac`

    > **Important**
    >
    > Make sure that you `CLASSPATH` includes `jaxb-xjc.jar` before
    > running `javac`.

5.  The resulting class files will contain your annotations as well
    other default annotations needed by the JAXB runtime binding
    framework

6.  Develop your client application that uses the data model and develop
    the code that uses the JAXB runtime binding framework to persist
    your data model using the (un)marshal operations.

7.  Compile and run your client application!

For more information about this process, see the the [Java WSDP
Tutorial](http://docs.oracle.com/javaee/6/tutorial/doc/gijti.html) and
the extensive [Sample Apps](#jaxb-2-0-sample-apps) documentation.

### Building and Running the Sample Apps with Ant {#section-3999932384958513}

To run the sample applications, just go into each sample directory, and
run `ant` without any option.

A few sample applications do *not* use Ant. For those samples, refer to
the included `readme.txt` files for instructions.

### List of Sample Apps {#samples}

`samples/catalog-resolver`

:   This example demonstrates how to use the `-catalog` compiler switch
    to handle references to schemas in external web sites.

`samples/character-escape`

:   This example shows how you can use the new JAXB RI `Marshaller`
    property `com.sun.xml.bind.characterEscapeHandler` to change the
    default character escaping behavior.

`samples/class-resolver`

:   This little DI-container-by-JAXB example demonstrates how one can
    avoid passing in a list of classes upfront, and instead load classes
    lazily.

`samples/create-marshal`

:   This sample application demonstrates how to use the `ObjectFactory`
    class to create a Java content tree from scratch and marshal it to
    XML data. It also demonstrates how to add content to a JAXB List
    property.

`samples/cycle-recovery`

:   JAXB RI\'s vendor extension `CycleRecoverable` provides application
    a hook to handle cycles in the object graph. Advanced.

`samples/datatypeconverter`

:   This sample application is very similar to the inline-customize
    sample application (formerly SampleApp6), but illustrates an easier,
    but not as robust, `<jaxb:javaType>` customization.

`samples/dtd`

:   This sample application illustrate some of the DTD support available
    in the JAXB RI\'s extension mode. Please refer to the
    [???](#jaxb-ri-extensions) page for more detail.

`samples/element-substitution`

:   This sample application illustrates how W3C XML Schema substitution
    groups are supported in JAXB RI\'s extension mode. Please refer to
    the [???](#jaxb-ri-extensions) page for more detail.

`samples/external-customize`

:   This sample application is identical to the datatypeconverter sample
    application (formerly SampleApp7) except that the binding
    customizations are contained in an external binding file.

`samples/fix-collides`

:   Another binding customization example that illustrates how to
    resolve name conflicts. Running this sample without the binding file
    will result in name collisions (see `readme.txt`) . Running ant will
    use the binding customizations to resolve the name conflicts while
    compiling the schema.

`samples/inline-customize`

:   This sample application demonstrates how to customize the default
    binding produced by the XJC binding compiler.

`samples/j2s-crete-marshal`

:   This sample application demonstrates marshalling, unmarshalling and
    unmarshal validation with existing Java classes annotated with JAXB
    annotations.

`samples/j2s-xmlAccessorOrder`

:   This sample application demonstrates the use of mapping annotations
    `@XmlAccessorOrder` and `@XmlType.propOrder` in Java classes for
    ordering properties and fields in Java to schema bindings.

`samples/j2s-xmlAdapter`

:   This sample application demonstrates the use of interface
    `XmlAdapter` and annotation `XmlJavaTypeAdapter` for custom
    marshaling/unmarshaling XML content into/out of a Java type.

`samples/j2s-xmlAttribute`

:   This sample application demonstrates the use of annotation
    `@XmlAttribute` for defining Java properties and fields as XML
    attributes.

`samples/j2s-xmlRootElement`

:   This sample application demonstrates the use of annotation
    `@XmlRootElement` to define a class to be an XML element.

`samples/j2s-xmlSchematType`

:   This sample application demonstrates the use of annotation
    `@XmlSchemaType` to customize the mapping of a property or field to
    an XML built-in type.

`samples/j2s-xmlType`

:   This sample application demonstrates the use of mapping annotations
    `@XmlAccessorOrder` and `@XmlType.propOrder` in Java classes for
    ordering properties and fields in Java to schema bindings.

`samples/locator-support`

:   This sample shows how to use the new non-standard locator support.
    By following the instructions in the readme.txt file, you can cause
    all of the generated impl classes to implement a new interface that
    provides more information about error locations. When a
    `ValidationEvent` happens on your content tree, simply retrieve the
    object and cast it down to `com.sun.xml.bind.extra.Locatable`.

`samples/modify-marshal`

:   This sample application demonstrates how to modify a java content
    tree and marshal it back to XML data.

`samples/namespace-prefix`

:   This sample application demonstrates how to use the new JAXB RI
    Marshaller property `com.sun.xml.bind.namespacePrefixMapper` to
    customize the namespace prefixes generated during marshalling.

`samples/partial-unmarshalling`

:   In this example, the input document will be unmarshalled a small
    chunk at a time, instead of unmarshalling the whole document at
    once.

`samples/pull-parser`

:   This sample app demonstrates how a pull-parser can be used with JAXB
    to increase the flexibility of processing.

`samples/streaming-unmarshalling`

:   This example illustrates a different approach to the streaming
    unmarshalling, which is suitable for processing a large document.

`samples/synchronized-methods`

:   This sample shows how to use the new non-standard synchronized
    method support. By following the instructions in the `readme.txt`,
    you can cause all of the generated impl class methods signatures to
    contain the `synchronized` keyword.

`samples/type-substitution`

:   This sample app demonstrates type substitution using the W3C XML
    Schema Part 0: Primer international purchase order schema.

`samples/ubl`

:   This project processes a UBL (Universal Business Language) order
    instance and prints a report to the screen.

`samples/unmarshal-read`

:   This sample application demonstrates how to unmarshal an instance
    document into a Java content tree and access data contained within
    it.

`samples/unmarshal-validate`

:   This sample application demonstrates how to enable validation during
    the unmarshal operations.

`samples/updateablePartialBind`

:   This sample application demonstrates how to partially map a DOM tree
    to JAXB (using JAXP 1.3 XPath), modify JAXB mapped instance and then
    update modifications back to the DOM tree.

`samples/vendor-extensions`

:   This example demonstrates how to use `<xjc:superClass>` vendor
    extensions provided by Sun\'s JAXB RI, as well as
    `<jaxb:serializable>` customization.

`samples/xml-channel`

:   This example demonstrates how one can use one communication channel
    (such as a socket) to send multiple XML messages, and how it can be
    combined with JAXB.

`samples/xml-stylesheet`

:   A common customization need for the marshalling output is about
    introducing extra processing instruction and/or `DOCTYPE`
    declaration. This example demonstrates how such modification can be
    done easily.