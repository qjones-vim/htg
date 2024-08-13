- [Getting Started](#getting-started)
  - [Charts](#charts)
    - [A Starter Chart](#a-starter-chart)
    - [A First Template](#a-first-template)
    - [Adding a Simple Template Call](#adding-a-simple-template-call)
- [Built-in Objects](#built-in-objects)
  - [Values](#values)
  - [Chart](#chart)
  - [Subcharts](#subcharts)
  - [Files](#files)
  - [Capabilities](#capabilities)
- [Values files](#values-files)
  - [Deleting a default key](#deleting-a-default-key)
- [Template Functions and Pipelines](#template-functions-and-pipelines)
  - [Pipelines](#pipelines)
    - [quote function](#quote-function)
    - [default function](#default-function)
    - [lookup function](#lookup-function)
  - [Operators are functions](#operators-are-functions)
  - [Template Function List](#template-function-list)
  - [The definition of empty](#the-definition-of-empty)
  - [swapcase algorithm](#swapcase-algorithm)
  - [Logic and Flow Control Functions](#logic-and-flow-control-functions)
  - [String Functions](#string-functions)
    - [General purpose](#general-purpose)
    - [Boolean](#boolean)
    - [Integer](#integer)
    - [Floating-point and complex constituents](#floating-point-and-complex-constituents)
    - [String and slice of bytes (treated equivalently with these verbs)](#string-and-slice-of-bytes-treated-equivalently-with-these-verbs)
    - [Slice](#slice)
  - [Type Conversion Functions](#type-conversion-functions)
    - [`atoi` Convert a string to an integer.](#atoi-convert-a-string-to-an-integer)
    - [`float64` Convert to a float64.](#float64-convert-to-a-float64)
    - [`int` Convert to an int at the system's width.](#int-convert-to-an-int-at-the-systems-width)
    - [`int64` Convert to an int64.](#int64-convert-to-an-int64)
    - [`toDecimal` Convert a unix octal to a int64](#todecimal-convert-a-unix-octal-to-a-int64)
    - [`toString` Convert to a string.](#tostring-convert-to-a-string)
    - [`toStrings` Convert a list, slice, or array to a list of strings.](#tostrings-convert-a-list-slice-or-array-to-a-list-of-strings)
    - [`toJson` `mustToJson` Convert list, slice, array, dict, or object to JSON.](#tojson-musttojson-convert-list-slice-array-dict-or-object-to-json)
    - [`toPrettyJson` `mustToPrettyJson` Convert list, slice, array, dict, or object to indented JSON.](#toprettyjson-musttoprettyjson-convert-list-slice-array-dict-or-object-to-indented-json)
    - [`toRawJson` `mustToRawJson` Convert list, slice, array, dict, or object to JSON with HTML characters unescaped.](#torawjson-musttorawjson-convert-list-slice-array-dict-or-object-to-json-with-html-characters-unescaped)
    - [`fromJson` `mustToJson` Convert a JSON string to an object.](#fromjson-musttojson-convert-a-json-string-to-an-object)
    - [`fromJsonArray` Convert a JSON array to a list.](#fromjsonarray-convert-a-json-array-to-a-list)
    - [`toYaml` Convert list, slice, array, dict, or object to indented yaml, can be used to copy chunks of yaml from any source.](#toyaml-convert-list-slice-array-dict-or-object-to-indented-yaml-can-be-used-to-copy-chunks-of-yaml-from-any-source)
    - [`toToml`Convert list, slice, array, dict, or object to toml, can be used to copy chunks of toml from any source.](#totomlconvert-list-slice-array-dict-or-object-to-toml-can-be-used-to-copy-chunks-of-toml-from-any-source)
    - [`fromYamlArray` Convert a YAML array to a list.](#fromyamlarray-convert-a-yaml-array-to-a-list)
    - [`toPrettyJson`, `mustToPrettyJson` The toPrettyJson function encodes an item into a pretty (indented) JSON string.](#toprettyjson-musttoprettyjson-the-toprettyjson-function-encodes-an-item-into-a-pretty-indented-json-string)
    - [`fromYaml` The fromYaml function takes a YAML string and returns an object that can be used in templates.](#fromyaml-the-fromyaml-function-takes-a-yaml-string-and-returns-an-object-that-can-be-used-in-templates)
    - [`fromJson` The fromJson function takes a JSON string and returns an object that can be used in templates.](#fromjson-the-fromjson-function-takes-a-json-string-and-returns-an-object-that-can-be-used-in-templates)
    - [`fromJsonArray`](#fromjsonarray)
    - [`fromYamlArray` The fromYamlArray function takes a YAML Array and returns a list that can be used in templates.](#fromyamlarray-the-fromyamlarray-function-takes-a-yaml-array-and-returns-a-list-that-can-be-used-in-templates)
  - [Regular Expressions](#regular-expressions)
    - [`regexMatch`, `mustRegexMatch` Returns true if the input string contains any match of the regular expression](#regexmatch-mustregexmatch-returns-true-if-the-input-string-contains-any-match-of-the-regular-expression)
    - [`regexFindAll`, `mustRegexFindAll` Returns a slice of all matches of the regular expression in the input string.](#regexfindall-mustregexfindall-returns-a-slice-of-all-matches-of-the-regular-expression-in-the-input-string)
    - [`regexFind`, `mustRegexFind` Return the first (left most) match of the regular expression in the input string](#regexfind-mustregexfind-return-the-first-left-most-match-of-the-regular-expression-in-the-input-string)
    - [`regexReplaceAll`, `mustRegexReplaceAll` Returns a copy of the input string, replacing matches of the Regexp with the replacement string replacement.](#regexreplaceall-mustregexreplaceall-returns-a-copy-of-the-input-string-replacing-matches-of-the-regexp-with-the-replacement-string-replacement)
    - [`regexReplaceAllLiteral`, `mustRegexReplaceAllLiteral` Returns a copy of the input string, replacing matches of the Regexp with the replacement string replacement.](#regexreplaceallliteral-mustregexreplaceallliteral-returns-a-copy-of-the-input-string-replacing-matches-of-the-regexp-with-the-replacement-string-replacement)
    - [`regexSplit`, `mustRegexSplit` Slices the input string into substrings separated by the expression and returns a slice of the substrings between those expression matches.](#regexsplit-mustregexsplit-slices-the-input-string-into-substrings-separated-by-the-expression-and-returns-a-slice-of-the-substrings-between-those-expression-matches)
  - [Cryptographic and Security Functions](#cryptographic-and-security-functions)
    - [`sha1sum` The sha1sum function receives a string, and computes it's SHA1 digest.](#sha1sum-the-sha1sum-function-receives-a-string-and-computes-its-sha1-digest)
    - [`sha256sum` The sha256sum function receives a string, and computes it's SHA256 digest.](#sha256sum-the-sha256sum-function-receives-a-string-and-computes-its-sha256-digest)
    - [`adler32sum` The adler32sum function receives a string, and computes its Adler-32 checksum.](#adler32sum-the-adler32sum-function-receives-a-string-and-computes-its-adler-32-checksum)
    - [`htpasswd` The htpasswd function takes a username and password and generates a bcrypt hash of the password.](#htpasswd-the-htpasswd-function-takes-a-username-and-password-and-generates-a-bcrypt-hash-of-the-password)
    - [`derivePassword` The derivePassword function can be used to derive a specific password based on some shared "master password" constraints.](#derivepassword-the-derivepassword-function-can-be-used-to-derive-a-specific-password-based-on-some-shared-master-password-constraints)
    - [`genPrivateKey` The genPrivateKey function generates a new private key encoded into a PEM block.](#genprivatekey-the-genprivatekey-function-generates-a-new-private-key-encoded-into-a-pem-block)
    - [`buildCustomCert` The buildCustomCert function allows customizing the certificate.](#buildcustomcert-the-buildcustomcert-function-allows-customizing-the-certificate)
    - [`genCA` The genCA function generates a new, self-signed x509 certificate authority.](#genca-the-genca-function-generates-a-new-self-signed-x509-certificate-authority)
    - [`genSelfSignedCert` The genSelfSignedCert function generates a new, self-signed x509 certificate.](#genselfsignedcert-the-genselfsignedcert-function-generates-a-new-self-signed-x509-certificate)
    - [`genSignedCert` The genSignedCert function generates a new, x509 certificate signed by the specified CA.](#gensignedcert-the-gensignedcert-function-generates-a-new-x509-certificate-signed-by-the-specified-ca)
    - [`encryptAES` The encryptAES function encrypts text with AES-256 CBC and returns a base64 encoded string.](#encryptaes-the-encryptaes-function-encrypts-text-with-aes-256-cbc-and-returns-a-base64-encoded-string)
    - [`decryptAES` The decryptAES function receives a base64 string encoded by the AES-256 CBC algorithm and returns the decoded text.](#decryptaes-the-decryptaes-function-receives-a-base64-string-encoded-by-the-aes-256-cbc-algorithm-and-returns-the-decoded-text)
  - [Date Functions](#date-functions)
    - [`now` The current date/time.](#now-the-current-datetime)
    - [`ago` The ago function returns duration from time. Now in seconds resolution.](#ago-the-ago-function-returns-duration-from-time-now-in-seconds-resolution)
  - [`date` The date function formats a date.](#date-the-date-function-formats-a-date)
    - [`dateInZone` Same as date, but with a timezone.](#dateinzone-same-as-date-but-with-a-timezone)
    - [duration](#duration)
    - [`durationRound` Rounds a given duration to the most significant unit.](#durationround-rounds-a-given-duration-to-the-most-significant-unit)
    - [`unixEpoch` Returns the seconds since the unix epoch for a `time.Time`](#unixepoch-returns-the-seconds-since-the-unix-epoch-for-a-timetime)
    - [`dateModify`, `mustDateModify` The dateModify takes a modification and a date and returns the timestamp.](#datemodify-mustdatemodify-the-datemodify-takes-a-modification-and-a-date-and-returns-the-timestamp)
    - [`htmlDate` The htmlDate function formats a date for inserting into an HTML date picker input field.](#htmldate-the-htmldate-function-formats-a-date-for-inserting-into-an-html-date-picker-input-field)
    - [`htmlDateInZone` Same as htmlDate, but with a timezone.](#htmldateinzone-same-as-htmldate-but-with-a-timezone)
    - [`toDate`, `mustToDate` toDate converts a string to a date.](#todate-musttodate-todate-converts-a-string-to-a-date)
  - [Dictionaries and Dict Functions](#dictionaries-and-dict-functions)
    - [`dict` Creaties a dictionary by calling the dict function and passing it a list of pairs](#dict-creaties-a-dictionary-by-calling-the-dict-function-and-passing-it-a-list-of-pairs)
    - [`get` Given a map and a key, get the value from the map.](#get-given-a-map-and-a-key-get-the-value-from-the-map)
    - [`set` Use set to add a new key/value pair to a dictionary.](#set-use-set-to-add-a-new-keyvalue-pair-to-a-dictionary)
    - [`unset` Given a map and a key, delete the key from the map.](#unset-given-a-map-and-a-key-delete-the-key-from-the-map)
    - [`hasKey` The hasKey function returns true if the given dict contains the given key.](#haskey-the-haskey-function-returns-true-if-the-given-dict-contains-the-given-key)
    - [`pluck` The pluck function makes it possible to give one key and multiple maps, and get a list of all of the matches:](#pluck-the-pluck-function-makes-it-possible-to-give-one-key-and-multiple-maps-and-get-a-list-of-all-of-the-matches)
    - [`dig` The dig function traverses a nested set of dicts, selecting keys from a list of values. It returns a default value if any of the keys are not found at the associated dict.](#dig-the-dig-function-traverses-a-nested-set-of-dicts-selecting-keys-from-a-list-of-values-it-returns-a-default-value-if-any-of-the-keys-are-not-found-at-the-associated-dict)
    - [`merge`, `mustMerge` Merge two or more dictionaries into one, giving precedence to the dest dictionary:](#merge-mustmerge-merge-two-or-more-dictionaries-into-one-giving-precedence-to-the-dest-dictionary)
    - [`mergeOverwrite`, `mustMergeOverwrite` Merge two or more dictionaries into one, giving precedence from right to left, effectively overwriting values in the dest dictionary:](#mergeoverwrite-mustmergeoverwrite-merge-two-or-more-dictionaries-into-one-giving-precedence-from-right-to-left-effectively-overwriting-values-in-the-dest-dictionary)
    - [`keys` The keys function will return a list of all of the keys in one or more dict types.](#keys-the-keys-function-will-return-a-list-of-all-of-the-keys-in-one-or-more-dict-types)
    - [`pick` The pick function selects just the given keys out of a dictionary, creating a new dict.](#pick-the-pick-function-selects-just-the-given-keys-out-of-a-dictionary-creating-a-new-dict)
    - [`omit` The omit function is similar to pick, except it returns a new dict with all the keys that do not match the given keys.](#omit-the-omit-function-is-similar-to-pick-except-it-returns-a-new-dict-with-all-the-keys-that-do-not-match-the-given-keys)
    - [`values` The values function is similar to keys, except it returns a new list with all the values of the source dict (only one dictionary is supported).](#values-the-values-function-is-similar-to-keys-except-it-returns-a-new-list-with-all-the-values-of-the-source-dict-only-one-dictionary-is-supported)
    - [`deepCopy`, `mustDeepCopy` The deepCopy and mustDeepCopy functions take a value and make a deep copy of the value.](#deepcopy-mustdeepcopy-the-deepcopy-and-mustdeepcopy-functions-take-a-value-and-make-a-deep-copy-of-the-value)
  - [Encoding Functions](#encoding-functions)
  - [Lists and List Functions](#lists-and-list-functions)
    - [`first`, `mustFirst` To get the head item on a list, use first.](#first-mustfirst-to-get-the-head-item-on-a-list-use-first)
    - [`rest`, `mustRest` To get the tail of the list (everything but the first item), use rest.](#rest-mustrest-to-get-the-tail-of-the-list-everything-but-the-first-item-use-rest)
    - [`last`, `mustLast` Get the last item on a list](#last-mustlast-get-the-last-item-on-a-list)
    - [`initial`, `mustInitial` return all but the last element.](#initial-mustinitial-return-all-but-the-last-element)
    - [`append`, `mustAppend` Append a new item to an existing list, creating a new list.](#append-mustappend-append-a-new-item-to-an-existing-list-creating-a-new-list)
    - [`prepend`, `mustPrepend` Push an element onto the front of a list, creating a new list.](#prepend-mustprepend-push-an-element-onto-the-front-of-a-list-creating-a-new-list)
  - [`concat` Concatenate arbitrary number of lists into one.](#concat-concatenate-arbitrary-number-of-lists-into-one)
    - [`reverse`, `mustReverse` Produce a new list with the reversed elements of the given list.](#reverse-mustreverse-produce-a-new-list-with-the-reversed-elements-of-the-given-list)
    - [`uniq`, `mustUniq` Generate a list with all of the duplicates removed.](#uniq-mustuniq-generate-a-list-with-all-of-the-duplicates-removed)
    - [`without`, `mustWithout` Filter items out of a list](#without-mustwithout-filter-items-out-of-a-list)
    - [`has`, `mustHas` Test to see if a list has a particular element.](#has-musthas-test-to-see-if-a-list-has-a-particular-element)
    - [`compact`, `mustCompact` Accepts a list and removes entries with empty values.](#compact-mustcompact-accepts-a-list-and-removes-entries-with-empty-values)
    - [`index` Get the nth element of a list](#index-get-the-nth-element-of-a-list)
    - [`slice`, `mustSlice` Get partial elements of a list](#slice-mustslice-get-partial-elements-of-a-list)
    - [`until` The until function builds a range of integers.](#until-the-until-function-builds-a-range-of-integers)
    - [`untilStep` Like until, untilStep generates a list of counting integers and allows you to define a start, stop, and step](#untilstep-like-until-untilstep-generates-a-list-of-counting-integers-and-allows-you-to-define-a-start-stop-and-step)
    - [`seq` print sequences of numbers](#seq-print-sequences-of-numbers)
  - [Math Functions](#math-functions)
    - [`add` Sum two or more inputs](#add-sum-two-or-more-inputs)
    - [`add1` To increment by 1](#add1-to-increment-by-1)
    - [`sub` To subtract](#sub-to-subtract)
    - [`div` Perform integer division](#div-perform-integer-division)
    - [`mod` Modulo with mod](#mod-modulo-with-mod)
    - [`mul` Multiply two or more inputs](#mul-multiply-two-or-more-inputs)
    - [`max` Return the largest of a series of integers](#max-return-the-largest-of-a-series-of-integers)
      - [`min` Return the smallest of a series of integers](#min-return-the-smallest-of-a-series-of-integers)
    - [`len` Returns the length of the argument as an integer](#len-returns-the-length-of-the-argument-as-an-integer)
  - [Float Math Functions](#float-math-functions)
    - [`addf` Sum numbers](#addf-sum-numbers)
    - [`add1f` To increment by 1](#add1f-to-increment-by-1)
    - [`subf` To subtract](#subf-to-subtract)
    - [`divf` Perform integer division](#divf-perform-integer-division)
    - [`mulf` Multiply with mulf](#mulf-multiply-with-mulf)
    - [`maxf` Return the largest of a series of floats](#maxf-return-the-largest-of-a-series-of-floats)
    - [`minf` Return the smallest of a series of floats.](#minf-return-the-smallest-of-a-series-of-floats)
    - [`floor` Returns the greatest float value less than or equal to input value.](#floor-returns-the-greatest-float-value-less-than-or-equal-to-input-value)
    - [`ceil` Returns the greatest float value greater than or equal to input value.](#ceil-returns-the-greatest-float-value-greater-than-or-equal-to-input-value)
    - [`round` Returns a float value with the remainder rounded to the given number to digits after the decimal point.](#round-returns-a-float-value-with-the-remainder-rounded-to-the-given-number-to-digits-after-the-decimal-point)
  - [Network Functions](#network-functions)
  - [File Path Functions](#file-path-functions)
    - [`base` Return the last element of a path](#base-return-the-last-element-of-a-path)
    - [`dir` Return the directory, stripping the last part of the path.](#dir-return-the-directory-stripping-the-last-part-of-the-path)
    - [`clean` Clean up a path](#clean-clean-up-a-path)
    - [`ext` Return the file extension](#ext-return-the-file-extension)
    - [`isAbs` check whether a file path is absolute](#isabs-check-whether-a-file-path-is-absolute)
  - [Reflection Functions](#reflection-functions)
  - [Kind Functions](#kind-functions)
    - [`kindOf` "hello" Verify that a value is a particular kind](#kindof-hello-verify-that-a-value-is-a-particular-kind)
  - [Type Functions](#type-functions)
    - [`typeOf` returns the underlying type of a value](#typeof-returns-the-underlying-type-of-a-value)
    - [`typeIs` Verify the value is of a particular type](#typeis-verify-the-value-is-of-a-particular-type)
    - [`typeIsLike`  Verify the value is of a particular type and also dereferences pointers](#typeislike--verify-the-value-is-of-a-particular-type-and-also-dereferences-pointers)
    - [`deepEqual` returns true if two values are "deeply equal"](#deepequal-returns-true-if-two-values-are-deeply-equal)
  - [Semantic Version Functions](#semantic-version-functions)
    - [`semver` The semver function parses a string into a Semantic Version:](#semver-the-semver-function-parses-a-string-into-a-semantic-version)
    - [`semverCompare` A more robust comparison function is provided as semverCompare. This version supports version ranges:](#semvercompare-a-more-robust-comparison-function-is-provided-as-semvercompare-this-version-supports-version-ranges)
  - [Basic Comparisons](#basic-comparisons)
  - [Working With Prerelease Versions](#working-with-prerelease-versions)
  - [Hyphen Range Comparisons](#hyphen-range-comparisons)
  - [Wildcards In Comparisons](#wildcards-in-comparisons)
  - [Tilde Range Comparisons (Patch)](#tilde-range-comparisons-patch)
  - [Caret Range Comparisons (Major)](#caret-range-comparisons-major)
  - [URL Functions](#url-functions)
    - [`urlParse` Parses string for URL and produces dict with URL parts](#urlparse-parses-string-for-url-and-produces-dict-with-url-parts)
    - [`urlJoin` Joins map (produced by urlParse) to produce URL string](#urljoin-joins-map-produced-by-urlparse-to-produce-url-string)
    - [`urlquery` Returns the escaped version of the value passed in as an argument so that it is suitable for embedding in the query portion of a URL.](#urlquery-returns-the-escaped-version-of-the-value-passed-in-as-an-argument-so-that-it-is-suitable-for-embedding-in-the-query-portion-of-a-url)
  - [UUID Functions](#uuid-functions)
    - [`uuidv4` The above returns a new UUID of the v4 (randomly generated) type.](#uuidv4-the-above-returns-a-new-uuid-of-the-v4-randomly-generated-type)
  - [Kubernetes and Chart Functions](#kubernetes-and-chart-functions)
    - [`lookup` lookup is used to look up resource in a running cluster.](#lookup-lookup-is-used-to-look-up-resource-in-a-running-cluster)
  - [File Functions](#file-functions)
- [Flow Control](#flow-control)
  - [If/Else](#ifelse)
  - [Controlling Whitespace](#controlling-whitespace)
  - [Modifying scope using with](#modifying-scope-using-with)
  - [Looping with the range action](#looping-with-the-range-action)
- [Variables](#variables)
- [Named Templates](#named-templates)
  - [Partials and \_ files](#partials-and-_-files)
  - [Declaring and using templates with define and template](#declaring-and-using-templates-with-define-and-template)
  - [Setting the scope of a template](#setting-the-scope-of-a-template)
  - [The include function](#the-include-function)
- [Accessing Files Inside Templates](#accessing-files-inside-templates)
  - [Basic example](#basic-example)
  - [Path helpers](#path-helpers)
  - [Glob patterns](#glob-patterns)
  - [ConfigMap and Secrets utility functions](#configmap-and-secrets-utility-functions)
  - [Encoding](#encoding)
  - [Lines](#lines)
- [Creating a NOTES.txt File](#creating-a-notestxt-file)
- [Subcharts and Global Values](#subcharts-and-global-values)
  - [Creating a Subchart](#creating-a-subchart)
  - [Adding Values and a Template to the Subchart](#adding-values-and-a-template-to-the-subchart)
  - [Overriding Values from a Parent Chart](#overriding-values-from-a-parent-chart)
  - [Global Chart Values](#global-chart-values)
  - [Sharing Templates with Subcharts](#sharing-templates-with-subcharts)
  - [Avoid Using Blocks](#avoid-using-blocks)
- [The .helmignore file](#the-helmignore-file)
- [Debugging Templates](#debugging-templates)
- [Next Steps](#next-steps)


# Getting Started
In this section of the guide, we'll create a chart and then add a first template. The chart we created here will be used throughout the rest of the guide.

To get going, let's take a brief look at a Helm chart.

## Charts
As described in the Charts Guide, Helm charts are structured like this:

```
mychart/
  Chart.yaml
  values.yaml
  charts/
  templates/
  ...
```

The `templates/` directory is for template files. 
- When Helm evaluates a chart, it will send all of the files in the `templates/` directory through the template rendering engine. 
- It then collects the results of those templates and sends them on to Kubernetes.

The `values.yaml` file is also important to templates. 
- This file contains the default values for a chart. 
- These values may be overridden by users during `helm install` or `helm upgrade`.

The `Chart.yaml` file contains a description of the chart. 
- You can access it from within a template.

The `charts/` directory may contain other charts (subcharts). 

### A Starter Chart
For this guide, we'll create a simple chart called `mychart`, and then we'll create some templates inside of the chart.

```
$ helm create mychart
```

A Quick Glimpse of `mychart/templates/`
- If you take a look at the mychart/templates/ directory, you'll notice a few files already there.

`NOTES.txt`
- The "help text" for your chart. 
- This will be displayed to your users when they run `helm install`.


`deployment.yaml`
-  A basic manifest for creating a Kubernetes deployment


`service.yaml`
- A basic manifest for creating a service endpoint for your deployment

`_helpers.tpl`
- A place to put template helpers that you can re-use throughout the chart


And what we're going to do is... remove them all! That way we can work through our tutorial from scratch. We'll actually create our own NOTES.txt and _helpers.tpl as we go.

```
$ rm -rf mychart/templates/*
```

When you're writing production grade charts, having basic versions of these charts can be really useful. So in your day-to-day chart authoring, you probably won't want to remove them.

### A First Template
The first template we are going to create will be a ConfigMap. In Kubernetes, a ConfigMap is simply an object for storing configuration data. Other things, like pods, can access the data in a ConfigMap.

Because ConfigMaps are basic resources, they make a great starting point for us.

Let's begin by creating a file called `mychart/templates/configmap.yaml`
```
apiVersion: v1
kind: ConfigMap
metadata:
  name: mychart-configmap
data:
  myvalue: "Hell World"
```

TIP: Template names do not follow a rigid naming pattern. However, we recommend using the extension `.yaml` for YAML files and `.tpl` for helpers.

The YAML file above is a bare-bones ConfigMap, having the minimal necessary fields. By virtue of the fact that this file is in the `mychart/templates/` directory, it will be sent through the template engine.

It is just fine to put a plain YAML file like this in the `mychart/templates/` directory. When Helm reads this template, it will simply send it to Kubernetes as-is.

With this simple template, we now have an installable chart. And we can install it like this

```
helm install full-coral ./mychart
```

Using Helm, we can retrieve the release and see the actual template that was loaded.

```
> helm install full-coral .
NAME: full-coral
LAST DEPLOYED: Thu Aug  8 15:57:53 2024
NAMESPACE: templating-tutorial
STATUS: deployed
REVISION: 1
TEST SUITE: None
```

Using Helm, we can retrieve the release and see the actual template that was loaded.
```
> helm get manifest full-coral
# Source: mychart/templates/configmap.yaml
---
apiVersion: v1
kind: ConfigMap
metadata:
  name: mychart-configmap
data:
  myvalue: "Hell World"
```

The `helm get manifest` command 
- takes a release name `(full-coral)` 
- prints out all of the Kubernetes resources that were uploaded to the server. 
- Each file begins with `---` to indicate the start of a YAML document, and then is followed by an automatically generated comment line that tells us what template file generated this YAML document.
- From there on, we can see that the YAML data is exactly what we put in our `configmap.yaml` file.

Now we can uninstall our release: `helm uninstall full-coral`
```
> helm uninstall full-coral
release "full-coral" uninstalled
```

### Adding a Simple Template Call
Hard-coding the name: into a resource is usually considered to be bad practice. Names should be unique to a release. So we might want to generate a name field by inserting the release name.

> TIP: The name: field is limited to 63 characters because of limitations to the DNS system. For that reason, release names are limited to 53 characters. Kubernetes 1.3 and earlier limited to only 24 characters (thus 14 character names).

Let's alter configmap.yaml accordingly.

```
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
```

The big change comes in the value of the name: field, which is now 
```yaml
{{ .Release.Name }}-configmap
```

> A template directive is enclosed in {{ and }} blocks.

The template directive `{{ .Release.Name }}` injects the release name into the template. The values that are passed into a template can be thought of as namespaced objects, where a dot `(.)` separates each namespaced element.

The leading dot before Release indicates that we start with the top-most namespace for this scope (we'll talk about scope in a bit). So we could read `.Release.Name` as "start at the top namespace, find the Release object, then look inside of it for an object called Name".


The `Release object` is one of the built-in objects for Helm, and we'll cover it in more depth later. But for now, it is sufficient to say that this will display the release name that the library assigns to our release.

Now when we install our resource, we'll immediately see the result of using this template directive:

```
> cat templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hell World"

> helm install clunky-serval .
NAME: clunky-serval
LAST DEPLOYED: Thu Aug  8 16:13:08 2024
NAMESPACE: templating-tutorial
STATUS: deployed
REVISION: 1
TEST SUITE: None

> helm get manifest clunky-serval
---
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: clunky-serval-configmap
data:
  myvalue: "Hell World"


> helm uninstall clunky-serval
release "clunky-serval" uninstalled
```

You can run helm get manifest clunky-serval to see the entire generated YAML.

Note that the ConfigMap inside Kubernetes name is clunky-serval-configmap instead of mychart-configmap previously.

At this point, we've seen templates at their most basic: YAML files that have template directives embedded in `{{ and }}`. In the next part, we'll take a deeper look into templates. But before moving on, there's one quick trick that can make building templates faster: When you want to test the template rendering, but not actually install anything, you can use `helm install --debug --dry-run goodly-guppy` ./mychart. This will render the templates. But instead of installing the chart, it will return the rendered template to you so you can see the output:


```
$ helm install --debug --dry-run goodly-guppy ./mychart
install.go:149: [debug] Original chart version: ""
install.go:166: [debug] CHART PATH: /Users/ninja/mychart

NAME: goodly-guppy
LAST DEPLOYED: Thu Dec 26 17:24:13 2019
NAMESPACE: default
STATUS: pending-install
REVISION: 1
TEST SUITE: None
USER-SUPPLIED VALUES:
{}

COMPUTED VALUES:
affinity: {}
fullnameOverride: ""
image:
  pullPolicy: IfNotPresent
  repository: nginx
imagePullSecrets: []
ingress:
  annotations: {}
  enabled: false
  hosts:
  - host: chart-example.local
    paths: []
  tls: []
nameOverride: ""
nodeSelector: {}
podSecurityContext: {}
replicaCount: 1
resources: {}
securityContext: {}
service:
  port: 80
  type: ClusterIP
serviceAccount:
  create: true
  name: null
tolerations: []

HOOKS:
MANIFEST:
---
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: goodly-guppy-configmap
data:
  myvalue: "Hello World"
```

Using `--dry-run` will make it easier to test your code, but it won't ensure that Kubernetes itself will accept the templates you generate. It's best not to assume that your chart will install just because `--dry-run` works.

In the Chart Template Guide, we take the basic chart we defined here and explore the Helm template language in detail. And we'll get started with built-in objects.

# Built-in Objects
Objects are passed into a template from the template engine. And your code can pass objects around (we'll see examples when we look at the `with` and `range` statements). There are even a few ways to create new objects within your templates, like with the `tuple` function we'll see later.

Objects can be simple, and have just one value. Or they can contain other objects or functions. For example, the Release object contains several objects (like `Release.Name`) and the `Files` object has a few functions.

In the previous section, we use `{{ .Release.Name }}` to insert the name of a release into a template. Release is one of the top-level objects that you can access in your templates.
 
- This object describes the release itself. It has several objects inside of it:
- `Release.Name`: The release name
- `Release.Namespace`: The namespace to be released into (if the manifest doesn’t override)
- `Release.IsUpgrade`: This is set to true if the current operation is an upgrade or rollback.
- `Release.IsInstall`: This is set to true if the current operation is an install.
- `Release.Revision`: The revision number for this release. On install, this is `1`, and it is incremented with each upgrade and rollback.
- `Release.Service`: The service that is rendering the present template. On Helm, this is always Helm.

## Values
Values passed into the template from the values.yaml file and from user-supplied files. By default, Values is empty.

## Chart
- The contents of the `Chart.yaml` file. 
- Any data in `Chart.yaml` will be accessible here. 
- For example `{{ .Chart.Name }}-{{ .Chart.Version }}` will print out the `mychart-0.1.0`.
- The available fields are listed in the [Charts Guide](https://helm.sh/docs/topics/charts/#the-chartyaml-file)


## Subcharts
- This provides access to the scope (`.Values`, `.Charts`, `.Releases` etc.) of subcharts to the parent.
-  For example `.Subcharts.mySubChart.myValue` to access the `myValue` in the `mySubChart` chart.

## Files
- This provides access to all non-special files in a chart. 
- While you cannot use it to access templates, you can use it to access other files in the chart.
- See the section [Accessing Files](https://helm.sh/docs/chart_template_guide/accessing_files/) for more.

| Function | Description  |
| --- | --- |
| `Files.Get` | get a file by name | (.Files.Get config.ini) |
| `Files.GetBytes` | is a function for getting the contents of a file as an array of bytes instead of as a string. This is useful for things like images. |
| `Files.Glob` | is a function that returns a list of files whose names match the given shell glob pattern.|
| `Files.Lines` | is a function that reads a file line-by-line. This is useful for iterating over each line in a file.|
| `Files.AsSecrets`|  is a function that returns the file bodies as Base 64 encoded strings. |
| `Files.AsConfig` | is a function that returns file bodies as a YAML map. |

## Capabilities
- This provides information about what capabilities the Kubernetes cluster supports.

| Function | Description| 
| --- | --- |
| `Capabilities.APIVersions` | is a set of versions.|
| `Capabilities.APIVersions.Has` | $version indicates whether a version (e.g., batch/v1) or resource (e.g., apps/v1/Deployment) is available on the cluster.|
| `Capabilities.KubeVersion` and `Capabilities.KubeVersion.Version` | is the Kubernetes version.|
| `Capabilities.KubeVersion.Major` | is the Kubernetes major version.|
| `Capabilities.KubeVersion.Minor` | is the Kubernetes minor version.|
| `Capabilities.HelmVersion` | is the object containing the Helm Version details, it is the same output of helm version.|
| `Capabilities.HelmVersion.Version` | is the current Helm version in semver format.|
| `Capabilities.HelmVersion.GitCommit` | is the Helm git `sha1`.|
| `Capabilities.HelmVersion.GitTreeState` | is the state of the Helm git tree.|
| `Capabilities.HelmVersion.GoVersion` | is the version of the Go compiler used. |

**Template**
- Contains information about the current template that is being executed

| Function | Description| 
| --- | --- |
| `Template.Name` | A namespaced file path to the current template (e.g. mychart/templates/mytemplate.yaml) |
| `Template.BasePath` | The namespaced path to the templates directory of the current chart (e.g. mychart/templates). |

The built-in values always begin with a capital letter. This is in keeping with Go's naming convention. When you create your own names, you are free to use a convention that suits your team. Some teams, like many whose charts you may see on [Artifact Hub](https://artifacthub.io/packages/search?kind=0), choose to use only initial lower case letters in order to distinguish local names from those built-in. In this guide, we follow that convention.


# Values files
The Values built in object provides access to values passed into the chart. Its contents come from multiple sources:

- The `values.yaml` file in the chart
- If this is a subchart, the `values.yaml` file of a parent chart
- A values file is passed into `helm install` or `helm upgrade` with the `-f` flag (`helm install -f myvals.yaml ./mychart`)
- Individual parameters are passed with `--set` (such as `helm install --set foo=bar ./mychart`)

The list above is in order of specificity: 
1. `values.yaml` is the default
2. `values.yaml` can be overridden by a parent chart's `values.yaml`
3. Parent chart `values.yaml` can be overridden by a user-supplied values file
4. user-supplied values file can be overridden by `--set` parameters.

Values files are plain YAML files. Let's edit `mychart/values.yaml` and then edit our ConfigMap template.

Removing the defaults in `values.yaml`, we'll set just one parameter
```
favoriteDrink: coffee
```

Now we can use this inside of a template:
```
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favoriteDrink }}
```

Notice on the last line we access `favoriteDrink` as an attribute of Values: `{{ .Values.favoriteDrink }}`.

Let's see how this renders.
```yaml
$ helm install geared-marsupi ./mychart --dry-run --debug
install.go:158: [debug] Original chart version: ""
install.go:175: [debug] CHART PATH: /home/bagratte/src/playground/mychart

NAME: geared-marsupi
LAST DEPLOYED: Wed Feb 19 23:21:13 2020
NAMESPACE: default
STATUS: pending-install
REVISION: 1
TEST SUITE: None
USER-SUPPLIED VALUES:
{}

COMPUTED VALUES:
favoriteDrink: coffee

HOOKS:
MANIFEST:
---
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: geared-marsupi-configmap
data:
  myvalue: "Hello World"
  drink: coffee
```

Because `favoriteDrink` is set in the default `values.yaml` file to coffee, that's the value displayed in the template. We can easily override that by adding a --set flag in our call to helm 
```yaml
$ helm install geared-marsupi ./mychart --dry-run --debug
install.go:158: [debug] Original chart version: ""
install.go:175: [debug] CHART PATH: /home/bagratte/src/playground/mychart

NAME: geared-marsupi
LAST DEPLOYED: Wed Feb 19 23:21:13 2020
NAMESPACE: default
STATUS: pending-install
REVISION: 1
TEST SUITE: None
USER-SUPPLIED VALUES:
{}

COMPUTED VALUES:
favoriteDrink: coffee

HOOKS:
MANIFEST:
---
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: geared-marsupi-configmap
data:
  myvalue: "Hello World"
  drink: coffee
```

Because favoriteDrink is set in the default values.yaml file to coffee, that's the value displayed in the template. We can easily override that by adding a --set flag in our call to helm install

```yaml
> helm install solid-vulture ./mychart --dry-run --debug --set favoriteDrink=slurm
install.go:222: [debug] Original chart version: ""
install.go:239: [debug] CHART PATH: /Users/quincyjones/workspace/scratch/helm_templating_guide/mychart

NAME: solid-vulture
LAST DEPLOYED: Thu Aug  8 17:13:03 2024
NAMESPACE: templating-tutorial
STATUS: pending-install
REVISION: 1
TEST SUITE: None
USER-SUPPLIED VALUES:
favoriteDrink: slurm

COMPUTED VALUES:
favoriteDrink: slurm

HOOKS:
MANIFEST:
---
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: solid-vulture-configmap
data:
  myvalue: "Hello World"
  drink: slurm
```

Since `--set` has a higher precedence than the default `values.yaml` file, our template generates `drink: slurm`.

Values files can contain more structured content, too. For example, we could create a favorite section in our `values.yaml` file, and then add several keys there:
```
favorite:
  drink: coffee
  food: pizza
```

Now we would have to modify the template slightly:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favorite.drink }}
  food: {{ .Values.favorite.food }}
```

While structuring data this way is possible, the recommendation is that you keep your values trees shallow, favoring flatness. When we look at assigning values to subcharts, we'll see how values are named using a tree structure.

## Deleting a default key
If you need to delete a key from the default values, you may override the value of the key to be `null`, in which case Helm will remove the key from the overridden values merge.

For example, the stable Drupal chart allows configuring the liveness probe, in case you configure a custom image. Here are the default values
```yaml
livenessProbe:
  httpGet:
    path: /user/login
    port: http
  initialDelaySeconds: 120
```

If you try to override the livenessProbe handler to `exec` instead of `httpGet` using `--set livenessProbe.exec.command=[cat,docroot/CHANGELOG.txt]`, Helm will coalesce the default and overridden keys together, resulting in the following YAML:
```yaml
livenessProbe:
  httpGet:
    path: /user/login
    port: http
  exec:
    command:
    - cat
    - docroot/CHANGELOG.txt
  initialDelaySeconds: 120
```
However, Kubernetes would then fail because you can not declare more than one `livenessProbe` handler. To overcome this, you may instruct Helm to delete the `livenessProbe.httpGet` by setting it to `null`:

```yaml
helm install stable/drupal --set image=my-registry/drupal:0.1.0 --set livenessProbe.exec.command=[cat,docroot/CHANGELOG.txt] --set livenessProbe.httpGet=null
```

At this point, we've seen several built-in objects, and used them to inject information into a template. Now we will take a look at another aspect of the template engine: functions and pipelines.

# Template Functions and Pipelines
So far, we've seen how to place information into a template. But that information is placed into the template unmodified. Sometimes we want to transform the supplied data in a way that makes it more useable to us.


Let's start with a best practice: When injecting strings from the `.Values` object into the template, we ought to quote these strings. We can do that by calling the `quote` function in the template directive
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ quote .Values.favorite.drink }}
  food: {{ quote .Values.favorite.food }}
```

Template functions follow the syntax `functionName arg1 arg2....` 
- In the snippet above, `quote .Values.favorite.drink `calls the quote function and passes it a single argument.

Helm has over 60 available functions. Some of them are defined by the [Go template language](https://godoc.org/text/template) itself. Most of the others are part of the [Sprig template library](https://masterminds.github.io/sprig/). We'll see many of them as we progress through the examples.

## Pipelines

One of the powerful features of the template language is its concept of pipelines. Drawing on a concept from UNIX, pipelines are a tool for chaining together a series of template commands to compactly express a series of transformations. In other words, pipelines are an efficient way of getting several things done in sequence. Let's rewrite the above example using a pipeline.

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favorite.drink | quote }}
  food: {{ .Values.favorite.food | quote }}
```

### quote function 
In this example, instead of calling `quote ARGUMENT`, we inverted the order. We "sent" the argument to the function using a pipeline `(|): .Values.favorite.drink | quote`. Using pipelines, we can chain several functions together:

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favorite.drink | quote }}
  food: {{ .Values.favorite.food | upper | quote }}
```

> Inverting the order is a common practice in templates. You will see `.val | quote` more often than `quote .val`. Either practice is fine.


When evaluated, that template will produce this:
```
> helm template bilbo ./mychart 
---
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMaps
metadata:
  name: bilbo-configmap
data:
  myvalue: "Hello World"
  drink: "pizza"
  food: "PIZZA"
```

Note that our original pizza has now been transformed to `"PIZZA"`.

When pipelining arguments like this, the result of the first evaluation (`.Values.favorite.drink`) is sent as the last argument to the function. We can modify the drink example above to illustrate with a function that takes two arguments: `repeat COUNT STRING`
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favorite.drink | repeat 5 | quote }}
  food: {{ .Values.favorite.food | upper | quote }}
```

The repeat function will echo the given string the given number of times, so we will get this for output:

```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: melting-porcup-configmap
data:
  myvalue: "Hello World"
  drink: "coffeecoffeecoffeecoffeecoffee"
  food: "PIZZA"
```

### default function

One function frequently used in templates is the default function: `default DEFAULT_VALUE GIVEN_VALUE`. This function allows you to specify a default value inside of the template, in case the value is omitted. Let's use it to modify the drink example above:

`values.yaml`
```yaml
favoriteDrink: coffee
favorite:
  drink: ""
  food: pizza
```

`configmap.yaml`
```yaml
apiVersion: v1
kind: ConfigMaps
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  food: {{ .Values.favorite.food | quote | upper }}
  drink: {{ .Values.favorite.drink | default "tea" | quote }}
```

output
```yaml
> helm template bilbo ./mychart 
---
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMaps
metadata:
  name: bilbo-configmap
data:
  myvalue: "Hello World"
  food: "PIZZA"
  drink: "tea"
```

In an actual chart, all static default values should live in the `values.yaml`, and should not be repeated using the default command (otherwise they would be redundant). However, the default command is perfect for computed values, which cannot be declared inside `values.yaml`. For example:

```yaml
drink: {{ .Values.favorite.drink | default (printf "%s-tea" (include "fullname" .)) }}
```

In some places, an `if` conditional guard may be better suited than default. We'll see those in the next section.

Template functions and pipelines are a powerful way to transform information and then insert it into your YAML. But sometimes it's necessary to add some template logic that is a little more sophisticated than just inserting a string. In the next section we will look at the control structures provided by the template language.

### lookup function
The lookup function can be used to look up resources in a running cluster. The synopsis of the lookup function is 
`lookup apiVersion, kind, namespace, name -> resource or resource list`.


|parameter|type| required | default |
|  --- | --- | --- | --- |
| apiVersion |	string | `true` |  |
| kind |	string | `true` |  |
| namespace |	string | `false` | "" |
| name |	string | `false` | "" |

> Both name and namespace are optional and can be passed as an empty string ("").

The following combination of parameters are possible:
`

|Behavior |	Lookup function |
| --- | --- |
|kubectl get pod mypod -n mynamespace	| lookup "v1" "Pod" "mynamespace" "mypod" |
|kubectl get pods -n mynamespace	| lookup "v1" "Pod" "mynamespace" "" |
|kubectl get pods --all-namespaces	| lookup "v1" "Pod" "" "" |
|kubectl get namespace mynamespace	| lookup "v1" "Namespace" "" "mynamespace" |
|kubectl get namespaces	| lookup "v1" "Namespace" "" ""    |


When lookup returns an object, it will return a dictionary. This dictionary can be further navigated to extract specific values.

The following example will return the annotations present for the mynamespace object:

```yaml
(lookup "v1" "Namespace" "" "mynamespace").metadata.annotations
```
When lookup returns a list of objects, it is possible to access the object list via the items field:

```yaml
{{ range $index, $service := (lookup "v1" "Service" "mynamespace" "").items }}
    {{/* do something with each service */}}
{{ end }}
```

When no object is found, an empty value is returned. This can be used to check for the existence of an object.

The lookup function uses Helm's existing Kubernetes connection configuration to query Kubernetes. If any error is returned when interacting with calling the API server (for example due to lack of permission to access a resource), Helm's template processing will fail.

Keep in mind that Helm is not supposed to contact the Kubernetes API Server during a `helm template|install|upgrade|delete|rollback --dry-run` operation. To test `lookup` against a running cluster, `helm template|install|upgrade|delete|rollback --dry-run=server` should be used instead to allow cluster connection.

## [Operators are functions](https://helm.sh/docs/chart_template_guide/functions_and_pipelines/#operators-are-functions)
For templates, the operators (`eq`, `ne`, `lt`, `gt`, `and`, `or` and ...) are all implemented as functions. In pipelines, operations can be grouped with parentheses `((, and ))`.

Now we can turn from functions and pipelines to flow control with conditions, loops, and scope modifiers.

## [Template Function List](https://helm.sh/docs/chart_template_guide/function_list/)
Helm includes many template functions you can take advantage of in templates. They are listed here and broken down by the following categories:


Template Function List
Helm includes many template functions you can take advantage of in templates. They are listed here and broken down by the following categories:


## The definition of empty
| Type | Empty value |
| --- | --- |
| Numeric | 0 |
| String | "" |
| Lists | [] |
| Dicts | {} |
| Boolean | false |
| nil |  null |

## swapcase algorithm
Upper case character converts to Lower case
Title case character converts to Lower case
Lower case character after Whitespace or at start converts to Title case
Other Lower case character converts to Upper case
Whitespace is defined by unicode.IsSpace(char)


## [Logic and Flow Control Functions](https://helm.sh/docs/chart_template_guide/function_list/#logic-and-flow-control-functions)
Helm includes numerous logic and control flow functions including and, coalesce, default, empty, eq, fail, ge, gt, le, lt, ne, not, or, and required.

> For structs, there is no definition of empty, so a struct will never return the default.

| name | description | usage example |
| --- | --- | --- |
| `and` | Returns the boolean AND of two or more arguments (the first empty argument, or the last argument). | `and .Arg1 .Arg2` | 
| `or` | Returns the boolean OR of two or more arguments (the first non-empty argument, or the last argument). | `or .Arg1 .Arg2` |
| `not` | Returns the boolean negation of its argument. | `not .Arg` |
| `eq` | Returns the boolean equality of the arguments (e.g., Arg1 == Arg2). | `eq .Arg1 .Arg2` |
| `ne` | Returns the boolean inequality of the arguments (e.g., Arg1 != Arg2) | `ne .Arg1 .Arg2` |
| `lt` | Returns a boolean true if the first argument is less than the second. False is returned otherwise (e.g., Arg1 < Arg2).| `lt .Arg1 .Arg2` |
| `le` | Returns a boolean true if the first argument is less than or equal to the second. False is returned otherwise (e.g., Arg1 <= Arg2). |  `le .Arg1 .Arg2` |
| `gt` |  Returns a boolean true if the first argument is greater than the second. False is returned otherwise (e.g., Arg1 > Arg2). | `gt .Arg1 .Arg2` |
| `ge` | Returns a boolean true if the first argument is greater than or equal to the second. False is returned otherwise (e.g., Arg1 >= Arg2). | `ge .Arg1 .Arg2` |
| `default` | To set a simple default value, use default, If .Bar evaluates to a non-empty value, it will be used. But if it is empty, foo will be returned instead. |  `default "foo" .Bar` | 
| `required`  | Specify values that must be set with required. In this example, If `.Bar` is empty or not defined, the template will not render and will return the error message supplied instead. see [The definition of "empty"](#the-definition-of-empty) | `required "A valid foo is required!" .Bar` |
| `empty` | The empty function returns true if the given value is considered empty, and false otherwise. The empty values are listed in the default section. see [The definition of "empty"](#the-definition-of-empty) . In Go template conditionals, emptiness is calculated for you. Thus, you rarely need `if not empty .Foo`. Instead, just use `if .Foo`. | `empty .Foo` |
| `fail`  | Unconditionally returns an empty string and an error with the specified text. This is useful in scenarios where other conditionals have determined that template rendering should fail. | `fail "Please accept the end user license agreement"` |
| `coalesce` | The coalesce function takes a list of values and returns the first non-empty one. This function is useful for scanning through multiple variables or values: `coalesce .name .parent.name "Matt"` The above will first check to see if `.name` is empty. If it is not, it will return that value. If it is empty, coalesce will evaluate `.parent.name` for emptiness. Finally, if both `.name` and `.parent.name` are empty, it will return `Matt`.| `coalesce 0 1 2`  returns 1 |
| `ternary` | The ternary function takes two values, and a test value. If the test value is true, the first value will be returned. If the test value is empty, the second value will be returned. This is similar to the ternary operator in C and other programming languages. | `true \| ternary "foo" "bar"` or `false \| ternary "foo" "bar"` |

## [String Functions](https://helm.sh/docs/chart_template_guide/function_list/#string-functions)
The placeholder to use depends on the type for the argument being passed in.

### General purpose
%v the value in a default format, when printing dicts, the plus flag `(%+v)` adds field names
%% a literal percent sign; consumes no value

### Boolean
| placeholer | description |
| --- | --- |
|`%t` | the word true or false |

### Integer
| placeholer | description |
| --- | --- |
| %b | base 2 |
| %c | the character represented by the corresponding Unicode code point |
| %d | base 10 |
| %o | base 8 |
| %O | base 8 with 0o prefix |
| %q | a single-quoted character literal safely escaped |
| %x | base 16, with lower-case letters for a-f |
| %X | base 16, with upper-case letters for A-F |
| %U | Unicode format: U+1234; same as "U+%04X" |

### Floating-point and complex constituents
| placeholer | description |
| --- | --- |
| %b | decimal less scientific notation with exponent a power of two, e.g. -123456p-78 | 
| %e | scientific notation, e.g. -1.234456e+78 | 
| %E | scientific notation, e.g. -1.234456E+78 | 
| %f | decimal point but no exponent, e.g. 123.456 | 
| %F | synonym for %f | 
| %g | %e for large exponents, %f otherwise. | 
| %G | %E for large exponents, %F otherwise | 
| %x | hexadecimal notation (with decimal power of two exponent), e.g. -0x1.23abcp+20 | 
| %X | upper-case hexadecimal notation, e.g. -0X1.23ABCP+20 | 

### String and slice of bytes (treated equivalently with these verbs)
| placeholer | description |
| --- | --- |
| %s  | the uninterpreted bytes of the string or slice |
| %q  | a double-quoted string safely escaped |
| %x  | base 16, lower-case, two characters per byte |
| %X  | base 16, upper-case, two characters per byte |

### Slice
| placeholer | description |
| --- | --- |
| %p  | address of 0th element in base 16 notation, with leading 0x |


| name | description | usage example |
| --- | --- | --- |
| `print` | Returns a string from the combination of its parts. Types that are not strings are converted to strings where possible. Note, when two arguments next to each other are not strings a space is added between them. |  `print "Matt has " Dogs " dogs"` |
| `println`  | Works the same way as print but adds a new line at the end. |  |
| `printf` |  Returns a string based on a formatting string and the arguments to pass to it in order. |  `printf "%s has %d dogs." .Name .NumberDogs` |
| `trim` |  The trim function removes white space from both sides of a string | `trim "   hello    "` returns `'hello'`| 
| `trimAll` | Removes the given characters from the front and back of a string | `trimAll "$" "$5.00"` returns `5.00` as a string |
| `trimPrefix` | Trim just the prefix from a string | `trimPrefix "-" "-hello"` returns `hello` |
| `trimSuffix` |  Trim just the suffix from a string | `trimSuffix "-" "hello-"` returns `hello` |
| `lower` | Convert the entire string to lowercase | lower "HELLO" returns `hello` |
| `upper` |  Convert the entire string to uppercase | `upper "hello"` returns `HELLO` |
| `title` |  Convert to title case | `title "hello world"` returns `Hello World` |
| `untitle` | Remove title casing|  `untitle "Hello World"` produces `hello world` |
| `repeat` | Repeat a string multiple times | `repeat 3 "hello"` returns `hellohellohello` |
| `substr` |  Get a substring from a string. It takes three parameters `start (int)`, `end (int)`, `string (string)` |  `substr 0 5 "hello world"` returns `hello` |
| `nospace` | Remove all whitespace from a string | `nospace "hello w o r l d"` returns `helloworld` |
| `trunc` | Truncate a string | `trunc 5 "hello world"` produces `hello` or `trunc -5 "hello world"` produces world |
| `abbrev` | Truncate a string with ellipses (...), Parameters: max length, the string | `abbrev 5 "hello world"`  returns `he...,` since it counts the width of the ellipses against the maximum length. |
| `abbrevboth` | Abbreviate both sides. It takes `*left offset*`, `*max length*`, `*the string*` | `abbrevboth 5 10 "1234 5678 9123"` | the above produces `...5678...`
| `initials` |  Given multiple words, take the first letter of each word and combine | `initials "First Try"` returns `FT` |
| `randAlphaNum` | generate cryptographically secure (uses crypto/rand) random strings | `randAlphaNum uses 0-9a-zA-Z` |
| `randAlpha` | generate cryptographically secure (uses crypto/rand) random strings | `randAlpha uses a-zA-Z` |
| `randNumeric` | generate cryptographically secure (uses crypto/rand) random strings | `randNumeric uses 0-9` | 
| `randAscii` |  generate cryptographically secure (uses crypto/rand) random strings. Uses all printable ASCII characters | `randNumeric 3` returns a random string with three digits |
| `wrap` |  Wrap text at a given column count | `wrap 80 $someText` will wrap the string in `$someText` at 80 columns. |
| `wrapWith` | wrapWith works as wrap, but lets you specify the string to wrap with. (wrap uses \n) |  `wrapWith 5 "\t" "Hello World"` returns  `Hello World` (where the whitespace is an ASCII tab character)
| `contains` |  Test to see if one string is contained inside of another | `contains "cat" "catch"` returns `true` because catch contains cat. |
| `hasPrefix` | The hasPrefix and hasSuffix functions test whether a string has a given prefix or suffix | hasPrefix "cat" "catch" returns `true` because catch has the prefix cat. |
| `hasSuffix` | The hasPrefix and hasSuffix functions test whether a string has a given prefix or suffix | hasSuffix "cat" "catch" returns `false` because catch has the prefix cat. |
| `quote`  | wrap a string in double quotes (quote)  |  |
| `squote` | wrap a string in single quotes (squote) |  |
| `cat` | The cat function concatenates multiple strings together into one, separating them with spaces |  cat "hello" "beautiful" "world" produces hello beautiful world |
| `indent` | The indent function indents every line in a given string to the specified indent width. This is useful when aligning multi-line strings | `indent 4 $lots_of_text` will indent every line of text by 4 space characters. |
| `nindent` | The nindent function is the same as the indent function, but prepends a new line to the beginning of the string. | `nindent 4 $lots_of_text` will indent every line of text by 4 space characters and add a new line to the beginning. |
| `replace` | Perform simple string replacement. It takes three arguments: `string to replace` `string to replace with` `source string` | `"I Am Henry VIII" \| replace " " "-"`  will produce `I-Am-Henry-VIII` |
| `plural` | Pluralize a string. The arguments are: `singular string` `plural string` `length integer` | `len $fish \| plural "one anchovy" "many anchovies"` if the length of the string is 1, the first argument will be printed (one anchovy). Otherwise, the second argument will be printed (many anchovies). |
| `snakecase` | Convert string from camelCase to snake_case. | `snakecase` `"FirstName"` returns produce `first_name` |
| `camelcase` | Convert string from snake_case to CamelCase | `camelcase "http_server"` returns `HttpServer` |
| `kebabcase` | Convert string from camelCase to kebab-case | `kebabcase "FirstName"` returns `first-name` |
| `swapcase` | Swap the case of a string using a word based algorithm swapcase | `"This Is A.Test"` returns `tHIS iS a.tEST` |
| `shuffle` | Shuffle a string | `shuffle "hello"` will randomize the letters in hello, perhaps producing `oelhl` |

## Type Conversion Functions
The following type conversion functions are provided by Helm:

### `atoi` Convert a string to an integer.
- Only atoi requires that the input be a specific type.
- The others will attempt to convert from any type to the destination type.
- For example, int64 can convert floats to ints, and it can also convert strings to ints.
### `float64` Convert to a float64.

### `int` Convert to an int at the system's width.

### `int64` Convert to an int64. 

### `toDecimal` Convert a unix octal to a int64
- `"0777" \| toDecimal` converts 0777 to 511 and returns the value as an int64.

### `toString` Convert to a string. 

### `toStrings` Convert a list, slice, or array to a list of strings.
- `list 1 2 3 \| toStrings` converts 1 to "1", 2 to "2", and so on, and then returns them as a list 

### `toJson` `mustToJson` Convert list, slice, array, dict, or object to JSON. 
- `toJson .Item` returns returns JSON string representation of `.Item`.

### `toPrettyJson` `mustToPrettyJson` Convert list, slice, array, dict, or object to indented JSON. 

### `toRawJson` `mustToRawJson` Convert list, slice, array, dict, or object to JSON with HTML characters unescaped. 
- `toRawJson .Item` returns unescaped JSON string representation of .Item

### `fromJson` `mustToJson` Convert a JSON string to an object. 
- The toJson function encodes an item into a JSON string.
- If the item cannot be converted to JSON the function will return an empty string.
- `mustToJson` will return an error in case the item cannot be encoded in JSON. 

### `fromJsonArray` Convert a JSON array to a list. 

### `toYaml` Convert list, slice, array, dict, or object to indented yaml, can be used to copy chunks of yaml from any source.
- This function is equivalent to GoLang `yaml.Marshal` function 
- see docs here: [Marshal](https://pkg.go.dev/gopkg.in/yaml.v2#Marshal)

### `toToml`Convert list, slice, array, dict, or object to toml, can be used to copy chunks of toml from any source.

### `fromYamlArray` Convert a YAML array to a list.

### `toPrettyJson`, `mustToPrettyJson` The toPrettyJson function encodes an item into a pretty (indented) JSON string.
- `toPrettyJson .Item` returns indented JSON string representation of .Item. |

### `fromYaml` The fromYaml function takes a YAML string and returns an object that can be used in templates.
```yaml
File at: yamls/person.yaml

name: Bob
age: 25
hobbies:
  - hiking
  - fishing
  - cooking
{{- $person := .Files.Get "yamls/person.yaml" | fromYaml }}
greeting: |
  Hi, my name is {{ $person.name }} and I am {{ $person.age }} years old.
  My hobbies are {{ range $person.hobbies }}{{ . }} {{ end }}.  
```

### `fromJson` The fromJson function takes a JSON string and returns an object that can be used in templates.
```yaml
File at: jsons/person.json

{
  "name": "Bob",
  "age": 25,
  "hobbies": [
    "hiking",
    "fishing",
    "cooking"
  ]
}
{{- $person := .Files.Get "jsons/person.json" | fromJson }}
greeting: |
  Hi, my name is {{ $person.name }} and I am {{ $person.age }} years old.
  My hobbies are {{ range $person.hobbies }}{{ . }} {{ end }}.  
```

### `fromJsonArray`
The fromJsonArray function takes a JSON Array and returns a list that can be used in templates.

```
File at: jsons/people.json

[
 { "name": "Bob","age": 25 },
 { "name": "Ram","age": 16 }
]
{{- $people := .Files.Get "jsons/people.json" | fromJsonArray }}
{{- range $person := $people }}
greeting: |
    Hi, my name is {{ $person.name }} and I am {{ $person.age }} years old.
{{ end }}
```

### `fromYamlArray` The fromYamlArray function takes a YAML Array and returns a list that can be used in templates.
```yaml
File at: yamls/people.yml

- name: Bob
  age: 25
- name: Ram
  age: 16
{{- $people := .Files.Get "yamls/people.yml" | fromYamlArray }}
{{- range $person := $people }}
greeting: |
    Hi, my name is {{ $person.name }} and I am {{ $person.age }} years old.
{{ end }}
```

## [Regular Expressions](https://helm.sh/docs/chart_template_guide/function_list/#regular-expressions)
### `regexMatch`, `mustRegexMatch` Returns true if the input string contains any match of the regular expression
- `regexMatch` `"^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,}$"` `"test@acme.com"` returns true
- `regexMatch` panics if there is a problem
- `mustRegexMatch` returns an error to the template engine if there is a problem.

### `regexFindAll`, `mustRegexFindAll` Returns a slice of all matches of the regular expression in the input string. 
- The last parameter `n` determines the number of substrings to return, where `-1` means return all matches
- `regexFindAll` `"[2,4,6,8]"` `"123456789"` `-1` produces  `[2 4 6 8]`
- `regexFindAll` panics if there is a problem 
- `mustRegexFindAll` returns an error to the template engine if there is a problem.

### `regexFind`, `mustRegexFind` Return the first (left most) match of the regular expression in the input string
- regexFind "[a-zA-Z][1-9]" "abcd1234"
- The above produces `d1`
- `regexFind` panics if there is a problem
- `mustRegexFind` returns an error to the template engine if there is a problem.

### `regexReplaceAll`, `mustRegexReplaceAll` Returns a copy of the input string, replacing matches of the Regexp with the replacement string replacement.
- Inside string replacement, $ signs are interpreted as in Expand, so for instance $1 represents the text of the first submatch
- regexReplaceAll "a(x*)b" "-ab-axxb-" "${1}W"
- The above produces `-W-xxW-`
- `regexReplaceAll` panics if there is a problem and `mustRegexReplaceAll` returns an error to the template engine if there is a problem.

### `regexReplaceAllLiteral`, `mustRegexReplaceAllLiteral` Returns a copy of the input string, replacing matches of the Regexp with the replacement string replacement.
- The replacement string is substituted directly, without using Expand
- regexReplaceAllLiteral "a(x*)b" "-ab-axxb-" "${1}"
- The above produces -${1}-${1}-
- `regexReplaceAllLiteral` panics if there is a problem and `mustRegexReplaceAllLiteral` returns an error to the template engine if there is a problem.

### `regexSplit`, `mustRegexSplit` Slices the input string into substrings separated by the expression and returns a slice of the substrings between those expression matches. 
- The last parameter n determines the number of substrings to return, where -1 means return all matches
- regexSplit "z+" "pizza" -1
- The above produces `[pi a]`
- regexSplit panics if there is a problem 
- mustRegexSplit returns an error to the template engine if there is a problem.

## Cryptographic and Security Functions
### `sha1sum` The sha1sum function receives a string, and computes it's SHA1 digest.
- sha1sum "Hello world!"

### `sha256sum` The sha256sum function receives a string, and computes it's SHA256 digest.
- sha256sum "Hello world!"
- The above will compute the SHA 256 sum in an "ASCII armored" format that is safe to print.

### `adler32sum` The adler32sum function receives a string, and computes its Adler-32 checksum.
adler32sum "Hello world!"

### `htpasswd` The htpasswd function takes a username and password and generates a bcrypt hash of the password. 
- The result can be used for basic authentication on an Apache HTTP Server.
- htpasswd "myUser" "myPassword"
- Note that it is insecure to store the password directly in the template.

### `derivePassword` The derivePassword function can be used to derive a specific password based on some shared "master password" constraints. 
- The algorithm for this is well specified.
- derivePassword 1 "long" "password" "user" "example.com"
- Note that it is considered insecure to store the parts directly in the template.

### `genPrivateKey` The genPrivateKey function generates a new private key encoded into a PEM block.
- It takes one of the values for its first param:
- ecdsa: Generate an elliptic curve DSA key (P256)
- dsa: Generate a DSA key (L2048N256)
- rsa: Generate an RSA 4096 key

### `buildCustomCert` The buildCustomCert function allows customizing the certificate.
- It takes the following string parameters:
  - A base64 encoded PEM format certificate
  - A base64 encoded PEM format private key
- It returns a certificate object with the following attributes:
  - Cert: A PEM-encoded certificate
  - Key: A PEM-encoded private key

Example:
```
$ca := buildCustomCert "base64-encoded-ca-crt" "base64-encoded-ca-key"
```
- Note that the returned object can be passed to the genSignedCert function to sign a certificate using this CA.

### `genCA` The genCA function generates a new, self-signed x509 certificate authority.

It takes the following parameters:
- Subject's common name (cn)
- Cert validity duration in days

It returns an object with the following attributes:
- Cert: A PEM-encoded certificate
- Key: A PEM-encoded private key

Example: 
```
$ca := genCA "foo-ca" 365
```


> Note that the returned object can be passed to the genSignedCert function to sign a certificate using this CA.

### `genSelfSignedCert` The genSelfSignedCert function generates a new, self-signed x509 certificate.
It takes the following parameters:

- Subject's common name (cn)
- Optional list of IPs; may be nil
- Optional list of alternate DNS names; may be nil
- Cert validity duration in days

It returns an object with the following attributes:
- Cert: A PEM-encoded certificate
- Key: A PEM-encoded private key

Example: 
```
$cert := genSelfSignedCert "foo.com" (list "10.0.0.1" "10.0.0.2") (list "bar.com" "bat.com") 365
```

### `genSignedCert` The genSignedCert function generates a new, x509 certificate signed by the specified CA.
It takes the following parameters:
- Subject's common name (cn)
- Optional list of IPs; may be nil
- Optional list of alternate DNS names; may be nil
- Cert validity duration in days
- CA (see genCA)

Example:
```
$ca := genCA "foo-ca" 365
$cert := genSignedCert "foo.com" (list "10.0.0.1" "10.0.0.2") (list "bar.com" "bat.com") 365 $ca
```

### `encryptAES` The encryptAES function encrypts text with AES-256 CBC and returns a base64 encoded string.
```
encryptAES "secretkey" "plaintext"
```

### `decryptAES` The decryptAES function receives a base64 string encoded by the AES-256 CBC algorithm and returns the decoded text.
```
"30tEfhuJSVRhpG97XCuWgz2okj7L8vQ1s6V9zVUPeDQ=" | decryptAES "secretkey"
```


## [Date Functions](https://helm.sh/docs/chart_template_guide/function_list/#date-functions)
### `now` The current date/time. 
Use this in conjunction with other date functions.

### `ago` The ago function returns duration from time. Now in seconds resolution.
- returns in `time.Duration` String() format

```
# returns 2h34m7s
ago .CreatedAt 
```


## `date` The date function formats a date.
Format the date to YEAR-MONTH-DAY:
```
now | date "2006-01-02"
```

- Date formatting in Go is a little bit different.
- In short, take this as the base date:
- `Mon Jan 2 15:04:05 MST 2006`
- Write it in the format you want. Above, 2006-01-02 is the same date, but in the format we want.

### `dateInZone` Same as date, but with a timezone.
```
dateInZone "2006-01-02" (now) "UTC"
```

### duration
Formats a given amount of seconds as a `time.Duration`.
```
duration "95"
```
This returns `1m35s`

### `durationRound` Rounds a given duration to the most significant unit. 
Strings and `time.Duration` gets parsed as a duration, while a `time.Time` is calculated as the duration since.

This return 2h
```
durationRound "2h10m5s"
```

This returns 3mo
```
durationRound "2400h10m5s"
```

### `unixEpoch` Returns the seconds since the unix epoch for a `time.Time`
```
now | unixEpoch
```

### `dateModify`, `mustDateModify` The dateModify takes a modification and a date and returns the timestamp.
Subtract an hour and thirty minutes from the current time:
```
now | dateModify "-1.5h"
```

- If the modification format is wrong dateModify will return the date unmodified. 
- `mustDateModify` will return an error otherwise.

### `htmlDate` The htmlDate function formats a date for inserting into an HTML date picker input field.
```
now | htmlDate
```

### `htmlDateInZone` Same as htmlDate, but with a timezone.
```
htmlDateInZone (now) "UTC"
```

### `toDate`, `mustToDate` toDate converts a string to a date. 
- The first argument is the date layout and the second the date string. 
- If the string can't be convert it returns the zero value.
- `mustToDate` will return an error in case the string cannot be converted.
- This is useful when you want to convert a string date to another format (using pipe). 
- The example below converts "2017-12-31" to "31/12/2017".
```
toDate "2006-01-02" "2017-12-31" | date "02/01/2006"
```

## Dictionaries and Dict Functions
Helm provides a key/value storage type called a dict (short for "dictionary", as in Python). 
- A `dict` is an unordered type.
- The key to a dictionary must be a string and the value can be any type, even another dict or list.
- `dicts` are mmutable therefore `set` and `unset` functions will modify the contents of a dictionary.

### `dict` Creaties a dictionary by calling the dict function and passing it a list of pairs
The following creates a dictionary with three items:
```
$myDict := dict "name1" "value1" "name2" "value2" "name3" "value 3"
```

### `get` Given a map and a key, get the value from the map.
> Note that if the key is not found, this operation will simply return "". No error will be generated.
```
get $myDict "name1"
```
The above returns "value1"


### `set` Use set to add a new key/value pair to a dictionary.
> Note that `set` returns the dictionary (a requirement of Go template functions), so you may need to trap the value as done above with the `$_` assignment.
```
$_ := set $myDict "name4" "value4"
```

### `unset` Given a map and a key, delete the key from the map.
As with set, this returns the dictionary.
> Note that if the key is not found, this operation will simply return. No error will be generated.
```
$_ := unset $myDict "name4"
```

### `hasKey` The hasKey function returns true if the given dict contains the given key.
```
hasKey $myDict "name1"
```
If the key is not found, this returns false.

### `pluck` The pluck function makes it possible to give one key and multiple maps, and get a list of all of the matches:
```
pluck "name1" $myDict $myOtherDict
```
- The above will return a list containing every found value ([value1 otherValue1]).
- If the given key is not found in a map, that map will not have an item in the list (and the length of the returned list will be less than the number of dicts in the call to pluck).
- If the key is found but the value is an empty value, that value will be inserted.
- A common idiom in Helm templates is to use pluck... | first to get the first matching key out of a collection of dictionaries.

### `dig` The dig function traverses a nested set of dicts, selecting keys from a list of values. It returns a default value if any of the keys are not found at the associated dict.
```
dig "user" "role" "humanName" "guest" $dict
```
Given a dict structured like
```json
{
  user: {
    role: {
      humanName: "curator"
    }
  }
}
```
- the above would return "curator". If the dict lacked even a user field, the result would be "guest".
- Dig can be very useful in cases where you'd like to avoid guard clauses, especially since Go's template package's and doesn't shortcut. 
- For instance and `a.maybeNil` `a.maybeNil.iNeedThis` will always evaluate `a.maybeNil.iNeedThis`, and panic if a lacks `a` `maybeNil` field.

> dig accepts its dict argument last in order to support pipelining. 

For instance:
```
merge a b c | dig "one" "two" "three" "<missing>"
```

### `merge`, `mustMerge` Merge two or more dictionaries into one, giving precedence to the dest dictionary:
Given:
```
dst:
  default: default
  overwrite: me
  key: true

src:
  overwrite: overwritten
  key: false
```

will result in:
```
newdict:
  default: default
  overwrite: me
  key: true
$newdict := merge $dst $src
```

- This is a deep merge operation but not a deep copy operation. 
- Nested objects that are merged are the same instance on both dicts. 
- If you want a deep copy along with the merge, then use the `deepCopy` function along with merging. For example,
```
deepCopy $source | merge $dest
```

- `mustMerge` will return an error in case of unsuccessful merge.

### `mergeOverwrite`, `mustMergeOverwrite` Merge two or more dictionaries into one, giving precedence from right to left, effectively overwriting values in the dest dictionary:

Given:
```
dst:
  default: default
  overwrite: me
  key: true

src:
  overwrite: overwritten
  key: false
will result in:

newdict:
  default: default
  overwrite: overwritten
  key: false
$newdict := mergeOverwrite $dest $source1 $source2
```

> This is a deep merge operation but not a deep copy operation. Nested objects that are merged are the same instance on both dicts. If you want a deep copy along with the merge then use the deepCopy function along with merging. For example,
```
deepCopy $source | mergeOverwrite $dest
```

- `mustMergeOverwrite` will return an error in case of unsuccessful merge.

### `keys` The keys function will return a list of all of the keys in one or more dict types. 
- Since a dictionary is unordered, the keys will not be in a predictable order.
- They can be sorted with `sortAlpha`.
```
keys $myDict | sortAlpha
```
- When supplying multiple dictionaries, the keys will be concatenated. 
- Use the `uniq` function along with `sortAlpha` to get a unique, sorted list of keys.
```
keys $myDict $myOtherDict | uniq | sortAlpha
```

### `pick` The pick function selects just the given keys out of a dictionary, creating a new dict.
```
$new := pick $myDict "name1" "name2"
```
The above returns `{name1: value1, name2: value2}`

### `omit` The omit function is similar to pick, except it returns a new dict with all the keys that do not match the given keys.
```
$new := omit $myDict "name1" "name3"
```
The above returns `{name2: value2}`

### `values` The values function is similar to keys, except it returns a new list with all the values of the source dict (only one dictionary is supported).
```
$vals := values $myDict
```
The above returns `list["value1", "value2", "value 3"]`. 
> Note that the values function gives no guarantees about the result ordering; if you care about this, then use `sortAlpha`.

### `deepCopy`, `mustDeepCopy` The deepCopy and mustDeepCopy functions take a value and make a deep copy of the value.
- This includes dicts and other structures. 
- `deepCopy` panics when there is a problem
- `mustDeepCopy` returns an error to the template system when there is an error
```
dict "a" 1 "b" 2 | deepCopy
```

> A Note on Dict Internals <br>
> - A dict is implemented in Go as a `map[string]interface{}`. 
> - Go developers can pass `map[string]interface{}` values into the context to make them available to templates as dicts.

## [Encoding Functions](https://helm.sh/docs/chart_template_guide/function_list/#encoding-functions)
Helm has the following encoding and decoding functions:

- `b64enc`/`b64dec`: Encode or decode with Base64
- `b32enc`/`b32dec`: Encode or decode with Base32

## [Lists and List Functions](https://helm.sh/docs/chart_template_guide/function_list/#lists-and-list-functions)
Helm provides a simple list type that can contain arbitrary sequential lists of data. This is similar to arrays or slices, but lists are designed to be used as immutable data types.

Create a list of integers:
```
$myList := list 1 2 3 4 5
```
The above creates a list of [1 2 3 4 5].

### `first`, `mustFirst` To get the head item on a list, use first.
```
first $myList 
```
The above returns 1

- `first` panics if there is a problem
- `mustFirst` returns an error to the template engine if there is a problem.

### `rest`, `mustRest` To get the tail of the list (everything but the first item), use rest.
```
rest $myList returns [2 3 4 5]
```

- `rest` panics if there is a problem
- `mustRest` returns an error to the template engine if there is a problem.

### `last`, `mustLast` Get the last item on a list
```
last $myList
```
- The above returns 5
- This is roughly analogous to reversing a list and then calling first.

### `initial`, `mustInitial` return all but the last element.
```yaml
initial $myList
```
- returns `[1 2 3 4]`
- initial panics if there is a problem, while mustInitial returns an error to the template engine if there is a problem.

### `append`, `mustAppend` Append a new item to an existing list, creating a new list.
```
$new = append $myList 6
```
- The above would set `$new` to `[1 2 3 4 5 6]` while `$myList` would remain unaltered.
- `append` panics if there is a problem 
- `mustAppend` returns an error to the template engine if there is a problem.

### `prepend`, `mustPrepend` Push an element onto the front of a list, creating a new list.
```
prepend $myList 0
```
- The above would produce [0 1 2 3 4 5]. $myList would remain unaltered.
- `prepend` panics if there is a problem, while `mustPrepend` returns an error to the template engine if there is a problem.

## `concat` Concatenate arbitrary number of lists into one.
```
concat $myList ( list 6 7 ) ( list 8 )
```
- The above would produce [1 2 3 4 5 6 7 8]. $myList would remain unaltered.

### `reverse`, `mustReverse` Produce a new list with the reversed elements of the given list.
```
reverse $myList
```
- The above would generate the list [5 4 3 2 1].
- reverse panics if there is a problem, while mustReverse returns an error to the template engine if there is a problem.

### `uniq`, `mustUniq` Generate a list with all of the duplicates removed.
```
list 1 1 1 2 | uniq
```
- The above would produce [1 2]
- uniq panics if there is a problem, while mustUniq returns an error to the template engine if there is a problem.

### `without`, `mustWithout` Filter items out of a list
```
without $myList 3
```
- The above would produce [1 2 4 5]
- without can take more than one filter:
```
without $myList 1 3 5
```
- That would produce [2 4]
- without panics if there is a problem, while mustWithout returns an error to the template engine if there is a problem.

### `has`, `mustHas` Test to see if a list has a particular element.
```
has 4 $myList
```
- The above would return true, while has "hello" $myList would return false.
- has panics if there is a problem, while mustHas returns an error to the template engine if there is a problem.

### `compact`, `mustCompact` Accepts a list and removes entries with empty values.
```
$list := list 1 "a" "foo" ""
$copy := compact $list
```
- compact will return a new list with the empty (i.e., "") item removed.
- compact panics if there is a problem and mustCompact returns an error to the template engine if there is a problem.

### `index` Get the nth element of a list
- To get the nth element of a list, use index list [n]. 
- To index into multi-dimensional lists, use index list [n] [m] ...
```
index $myList 0 returns 1. It is the same as myList[0]
index $myList 0 1 would be the same as myList[0][1]
```

### `slice`, `mustSlice` Get partial elements of a list
- To get partial elements of a list, use slice list [n] [m]. 
- It is equivalent of list[n:m].
```
slice $myList returns [1 2 3 4 5]. It is same as myList[:].
slice $myList 3 returns [4 5]. It is same as myList[3:].
slice $myList 1 3 returns [2 3]. It is same as myList[1:3].
slice $myList 0 3 returns [1 2 3]. It is same as myList[:3].
slice panics if there is a problem, while mustSlice returns an error to the template engine if there is a problem.
```

### `until` The until function builds a range of integers.
```
until 5
The above generates the list [0, 1, 2, 3, 4].
```
- This is useful for looping with range $i, $e := until 5

### `untilStep` Like until, untilStep generates a list of counting integers and allows you to define a start, stop, and step
```
untilStep 3 6 2
```
- The above will produce [3 5] by starting with 3, and adding 2 until it is equal or greater than 6. 
- This is similar to Python's range function.

### `seq` print sequences of numbers
1. parameter (end) - will generate all counting integers between 1 and end inclusive.
2. parameters (start, end) - will generate all counting integers between start and end inclusive incrementing or decrementing by 1.
3. parameters (start, step, end) - will generate all counting integers between start and end inclusive incrementing or decrementing by step.

```
seq 5       => 1 2 3 4 5
seq -3      => 1 0 -1 -2 -3
seq 0 2     => 0 1 2
seq 2 -2    => 2 1 0 -1 -2
seq 0 2 10  => 0 2 4 6 8 10
seq 0 -2 -5 => 0 -2 -4
```

## Math Functions

### `add` Sum two or more inputs
### `add1` To increment by 1
### `sub` To subtract
### `div` Perform integer division
### `mod` Modulo with mod
### `mul` Multiply two or more inputs
### `max` Return the largest of a series of integers
#### `min` Return the smallest of a series of integers
### `len` Returns the length of the argument as an integer

## Float Math Functions
All math functions operate on float64 values

### `addf` Sum numbers
### `add1f` To increment by 1
### `subf` To subtract
### `divf` Perform integer division
### `mulf` Multiply with mulf
### `maxf` Return the largest of a series of floats
### `minf` Return the smallest of a series of floats.
### `floor` Returns the greatest float value less than or equal to input value.
```
floor 123.9999 will return 123.0.
```

### `ceil` Returns the greatest float value greater than or equal to input value.
```
ceil 123.001 will return 124.0.
```
### `round` Returns a float value with the remainder rounded to the given number to digits after the decimal point.
```
round 123.555555 3 will return 123.556.
```

## Network Functions
- Helm has a single network function, getHostByName.
  - The getHostByName receives a domain name and returns the ip address.
```
getHostByName "www.google.com" 
```
The above would return the corresponding ip address of `www.google.com`.

## File Path Functions
While Helm template functions do not grant access to the filesystem, they do provide functions for working with strings that follow file path conventions. 

### `base` Return the last element of a path
```
base "foo/bar/baz"
```
The above prints "baz"

### `dir` Return the directory, stripping the last part of the path. 
```
dir "foo/bar/baz"
```
The above would return `foo/bar`

### `clean` Clean up a path
```
clean "foo/bar/../baz"
```
The above resolves the .. and returns foo/baz.

### `ext` Return the file extension
```
ext "foo.bar"
```
The above returns `.bar`

### `isAbs` check whether a file path is absolute

## Reflection Functions
- Helm provides rudimentary reflection tools. These help advanced template developers understand the underlying Go type information for a particular value. Helm is written in Go and is strongly typed. The type system applies within templates.
- Go has several primitive kinds, like string, slice, int64, and bool. 
- Go has an open type system that allows developers to create their own types.
- Helm provides a set of functions for each via kind functions and type functions. 
- A `deepEqual` function is also provided to compare to values.

## Kind Functions
### `kindOf` "hello" Verify that a value is a particular kind
```
kindIs "int" 123
```
The above will return true.

## Type Functions
- Types are slightly harder to work with, so there are three different functions:

### `typeOf` returns the underlying type of a value
```
typeOf $foo
```

### `typeIs` Verify the value is of a particular type 
```
typeIs "*io.Buffer" $myVal
```

### `typeIsLike`  Verify the value is of a particular type and also dereferences pointers
- Note: None of these can test whether or not something implements a given interface, since doing so would require compiling the interface in ahead of time.

### `deepEqual` returns true if two values are "deeply equal" 
- Works for non-primitive types as well (compared to the built-in eq)

deepEqual (list 1 2 3) (list 1 2 3)

The above will return true.

## Semantic Version Functions
- Some version schemes are easily parseable and comparable. 
- Helm provides functions for working with SemVer 2 versions. 

### `semver` The semver function parses a string into a Semantic Version:
```
$version := semver "1.2.3-alpha.1+123"
```
- If the parser fails, it will cause template execution to halt with an error.

At this point, $version is a pointer to a Version object with the following properties:
```
$version.Major: The major number (1 above)
$version.Minor: The minor number (2 above)
$version.Patch: The patch number (3 above)
$version.Prerelease: The prerelease (alpha.1 above)
$version.Metadata: The build metadata (123 above)
$version.Original: The original version as a string
```
Additionally, you can compare a Version to another version using the Compare function:
```
semver "1.4.3" | (semver "1.2.3").Compare
```

The above will return -1.

The return values are:
```
-1 if the given semver is greater than the semver whose Compare method was called
1 if the version who's Compare function was called is greater.
0 if they are the same version
(Note that in SemVer, the Metadata field is not compared during version comparison operations.)
```

### `semverCompare` A more robust comparison function is provided as semverCompare. This version supports version ranges:
Checks for an exact match
```
semverCompare "1.2.3" "1.2.3" 
```

Checks that the major and minor versions match, and that the patch number of the second version is greater than or equal to the first parameter
```
semverCompare "~1.2.0" "1.2.3" 
```
> The SemVer functions use the Masterminds semver library, from the creators of Sprig.

## Basic Comparisons
- There are two elements to the comparisons. 
  - First, a comparison string is a list of space or comma separated AND comparisons. 
  - These are then separated by || (OR) comparisons. 
  - For example, `">= 1.2 < 3.0.0 || >= 4.2.3"` is looking for a comparison that's greater than or equal to 1.2 and less than 3.0.0 or is greater than or equal to 4.2.3.

The basic comparisons are:
```
=: equal (aliased to no operator)
!=: not equal
>: greater than
<: less than
>=: greater than or equal to
<=: less than or equal to
```

## Working With Prerelease Versions
- Pre-releases, for those not familiar with them, are used for software releases prior to stable or generally available releases. 
  - Examples of prereleases include development, alpha, beta, and release candidate releases. 
- A prerelease may be a version such as `1.2.3-beta.1`
- A stable release release would be `1.2.3`. 
- In the order of precedence, prereleases come before their associated releases. 
  - In this example 1.2.3-beta.1 < 1.2.3.
  - According to the Semantic Version specification prereleases may not be API compliant with their release counterpart. It says, A pre-release version indicates that the version is unstable and might not satisfy the intended compatibility requirements as denoted by its associated normal version.
SemVer comparisons using constraints without a prerelease comparator will skip prerelease versions. For example, >=1.2.3 will skip prereleases when looking at a list of releases, while >=1.2.3-0 will evaluate and find prereleases.

- The reason for the 0 as a pre-release version in the example comparison is because pre-releases can only contain ASCII alphanumerics and hyphens (along with . separators), per the spec. 
- Sorting happens in ASCII sort order, again per the spec. 
- The lowest character is a 0 in ASCII sort order (see an ASCII Table)
- Understanding ASCII sort ordering is important because A-Z comes before a-z. 
- That means `>=1.2.3-BETA` will return `1.2.3-alpha`. 
- What you might expect from case sensitivity doesn't apply here. 
- This is due to ASCII sort ordering which is what the spec specifies.

## Hyphen Range Comparisons
There are multiple methods to handle ranges and the first is hyphens ranges. These look like:
```
1.2 - 1.4.5 which is equivalent to >= 1.2 <= 1.4.5
2.3.4 - 4.5 which is equivalent to >= 2.3.4 <= 4.5
```

## Wildcards In Comparisons
- The x, X, and * characters can be used as a wildcard character. 
- This works for all comparison operators. 
- When used on the `=` operator it falls back to the patch level comparison (see tilde below). 
For example, 
```
1.2.x is equivalent to >= 1.2.0, < 1.3.0
>= 1.2.x is equivalent to >= 1.2.0
<= 2.x is equivalent to < 3
* is equivalent to >= 0.0.0
```

## Tilde Range Comparisons (Patch)
The tilde (~) comparison operator is for patch level ranges when a minor version is specified and major level changes when the minor number is missing. For example,
```
~1.2.3 is equivalent to >= 1.2.3, < 1.3.0
~1 is equivalent to >= 1, < 2
~2.3 is equivalent to >= 2.3, < 2.4
~1.2.x is equivalent to >= 1.2.0, < 1.3.0
~1.x is equivalent to >= 1, < 2
```

## Caret Range Comparisons (Major)
The caret (^) comparison operator is for major level changes once a stable (1.0.0) release has occurred. Prior to a 1.0.0 release the minor versions acts as the API stability level. This is useful when comparisons of API versions as a major change is API breaking. For example,
```
^1.2.3 is equivalent to >= 1.2.3, < 2.0.0
^1.2.x is equivalent to >= 1.2.0, < 2.0.0
^2.3 is equivalent to >= 2.3, < 3
^2.x is equivalent to >= 2.0.0, < 3
^0.2.3 is equivalent to >=0.2.3 <0.3.0
^0.2 is equivalent to >=0.2.0 <0.3.0
^0.0.3 is equivalent to >=0.0.3 <0.0.4
^0.0 is equivalent to >=0.0.0 <0.1.0
^0 is equivalent to >=0.0.0 <1.0.0
```

## URL Functions
### `urlParse` Parses string for URL and produces dict with URL parts
```
urlParse "http://admin:secret@server.com:8080/api?list=false#anchor"
```
The above returns a dict, containing URL object:
```
scheme:   'http'
host:     'server.com:8080'
path:     '/api'
query:    'list=false'
opaque:   nil
fragment: 'anchor'
userinfo: 'admin:secret'
```

> This is implemented used the URL packages from the Go standard library. For more info, check https://golang.org/pkg/net/url/#URL

### `urlJoin` Joins map (produced by urlParse) to produce URL string
```
urlJoin (dict "fragment" "fragment" "host" "host:80" "path" "/path" "query" "query" "scheme" "http")
```
The above returns the following string:
```
http://host:80/path?query#fragment
```

### `urlquery` Returns the escaped version of the value passed in as an argument so that it is suitable for embedding in the query portion of a URL.
```
$var := urlquery "string for query"
```

## UUID Functions
Helm can generate UUID v4 universally unique IDs.

### `uuidv4` The above returns a new UUID of the v4 (randomly generated) type.

## Kubernetes and Chart Functions
Helm includes functions for working with Kubernetes including .Capabilities.APIVersions.Has, Files, and lookup.

### `lookup` lookup is used to look up resource in a running cluster. 
- When used with the helm template command it always returns an empty response.
- You can find more detail in the documentation on the lookup function.
```
.Capabilities.APIVersions.Has
```
Returns if an API version or resource is available in a cluster.
```
.Capabilities.APIVersions.Has "apps/v1"
.Capabilities.APIVersions.Has "apps/v1/Deployment"
```
More information is available on the built-in object documentation.

## File Functions
- There are several functions that enable you to get to non-special files within a chart. 
- For example, to access application configuration files. 
- These are documented in Accessing Files Inside Templates.
- Note, the documentation for many of these functions come from Sprig. 
- [Sprig](https://github.com/Masterminds/sprig) is a template function library available to Go applications.


# Flow Control
- Control structures (called "actions" in template parlance) provide you, the template author, with the ability to control the flow of a template's generation. 
- Helm's template language provides the following control structures:
  - `if/else` for creating conditional blocks
  - `with` to specify a scope
  - `range`, which provides a "for each"-style loop
- In addition to these, it provides a few actions for declaring and using named template segments:
  - `define` declares a new named template inside of your template
  - `template` imports a named template
  - `block` declares a special kind of fillable template area

- In this section, we'll talk about `if`, `with`, and `range`. 

## If/Else
- The first control structure we'll look at is for conditionally including blocks of text in a template. 
- This is the `if/else` block.
- The basic structure for a conditional looks like this:
```yaml
{{ if PIPELINE }}
  # Do something
{{ else if OTHER PIPELINE }}
  # Do something else
{{ else }}
  # Default case
{{ end }}
```

- Notice that we're now talking about pipelines instead of values. 
- The reason for this is to make it clear that control structures can execute an entire pipeline, not just evaluate a value.

- A pipeline is evaluated as false if the value is:
  - a boolean false
  - a numeric zero
  - an empty string
  - a nil (empty or null)
  - an empty collection (map, slice, tuple, dict, array)
- Under all other conditions, the condition is true.
- Let's add a simple conditional to our ConfigMap. We'll add another setting if the drink is set to coffee:

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favorite.drink | default "tea" | quote }}
  food: {{ .Values.favorite.food | upper | quote }}
  {{ if eq .Values.favorite.drink "coffee" }}mug: "true"{{ end }}
```

Since we commented out drink: coffee in our last example, the output should not include a mug: "true" flag. But if we add that line back into our values.yaml file, the output should look like this:

```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: eyewitness-elk-configmap
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "PIZZA"
  mug: "true"
```

## Controlling Whitespace
While we're looking at conditionals, we should take a quick look at the way whitespace is controlled in templates. Let's take the previous example and format it to be a little easier to read:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favorite.drink | default "tea" | quote }}
  food: {{ .Values.favorite.food | upper | quote }}
  {{ if eq .Values.favorite.drink "coffee" }}
    mug: "true"
  {{ end }}
```

Initially, this looks good. But if we run it through the template engine, we'll get an unfortunate result:
```shell
$ helm install --dry-run --debug ./mychart
SERVER: "localhost:44134"
CHART PATH: /Users/mattbutcher/Code/Go/src/helm.sh/helm/_scratch/mychart
Error: YAML parse error on mychart/templates/configmap.yaml: error converting YAML to JSON: yaml: line 9: did not find expected key
What happened? We generated incorrect YAML because of the whitespacing above.


# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: eyewitness-elk-configmap
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "PIZZA"
    mug: "true"
```

mug is incorrectly indented. Let's simply out-dent that one line, and re-run:

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favorite.drink | default "tea" | quote }}
  food: {{ .Values.favorite.food | upper | quote }}
  {{ if eq .Values.favorite.drink "coffee" }}
  mug: "true"
  {{ end }}
```

When we sent that, we'll get YAML that is valid, but still looks a little funny:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: telling-chimp-configmap
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "PIZZA"

  mug: "true"
```
- Notice that we received a few empty lines in our YAML. 
- Why? When the template engine runs, it removes the contents inside of {{ and }}, but it leaves the remaining whitespace exactly as is.
- YAML ascribes meaning to whitespace, so managing the whitespace becomes pretty important. 
- Fortunately, Helm templates have a few tools to help.

- First, the curly brace syntax of template declarations can be modified with special characters to tell the template engine to chomp whitespace. 
  - `{{-` `(with the dash and space added)` indicates that whitespace should be chomped left
  - `-}}` means whitespace to the right should be consumed. 
  - Be careful! Newlines are whitespace!
- Make sure there is a space between the `-` and the rest of your directive. `{{- 3 }}` means "trim left whitespace and print 3" while `{{-3 }}` means `"print -3"`.
- Using this syntax, we can modify our template to get rid of those new lines:
```
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favorite.drink | default "tea" | quote }}
  food: {{ .Values.favorite.food | upper | quote }}
  {{- if eq .Values.favorite.drink "coffee" }}
  mug: "true"
  {{- end }}
```

- Just for the sake of making this point clear, let's adjust the above, and substitute an * for each whitespace that will be deleted following this rule.
- An * at the end of the line indicates a newline character that would be removed
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  drink: {{ .Values.favorite.drink | default "tea" | quote }}
  food: {{ .Values.favorite.food | upper | quote }}*
**{{- if eq .Values.favorite.drink "coffee" }}
  mug: "true"*
**{{- end }}
```

Keeping that in mind, we can run our template through Helm and see the result:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: clunky-cat-configmap
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "PIZZA"
  mug: "true"
```

Be careful with the chomping modifiers. It is easy to accidentally do things like this:
```yaml
  food: {{ .Values.favorite.food | upper | quote }}
  {{- if eq .Values.favorite.drink "coffee" -}}
  mug: "true"
  {{- end -}}
```

- That will produce food: "PIZZA"mug: "true" because it consumed newlines on both sides.
- For the details on whitespace control in templates, see the [Official Go template documentation](https://pkg.go.dev/text/template?utm_source=godoc)


Finally, sometimes it's easier to tell the template system how to indent for you instead of trying to master the spacing of template directives. 
- For that reason, you may sometimes find it useful to use the indent function `({{ indent 2 "mug:true" }})`.

## [Modifying scope using with](https://helm.sh/docs/chart_template_guide/control_structures/#modifying-scope-using-with)
- The next control structure to look at is the with action. 
- This controls variable scoping. 
- Recall that `.` is a reference to the current scope. 
- So `.Values` tells the template to find the Values object in the current scope.
- The syntax for with is similar to a simple if statement:
```
{{ with PIPELINE }}
  # restricted scope
{{ end }}
```

Scopes can be changed. 
- `with` can allow you to set the current scope (.) to a particular object. 
- For example, we've been working with `.Values.favorite` Let's rewrite our ConfigMap to alter the `.` scope to point to `.Values.favorite`:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  {{- with .Values.favorite }}
  drink: {{ .drink | default "tea" | quote }}
  food: {{ .food | upper | quote }}
  {{- end }}
```
> Note that we removed the if conditional from the previous exercise because it is now unnecessary - the block after with only executes if the value of PIPELINE is not empty.
- Notice that now we can reference `.drink` and `.food` without qualifying them. 
- That is because the `with` statement sets `.` to point to `.Values.favorite`. 
- The `.` is reset to its previous scope after `{{ end }}`.

> But here's a note of caution! Inside of the restricted scope, you will not be able to access the other objects from the parent scope using .. This, for example, will fail:
```yaml
  {{- with .Values.favorite }}
  drink: {{ .drink | default "tea" | quote }}
  food: {{ .food | upper | quote }}
  release: {{ .Release.Name }}
  {{- end }}
```
- It will produce an error because `Release.Name` is not inside of the restricted scope for .. However, if we swap the last two lines, all will work as expected because the scope is reset after {{ end }}.
```yaml
  {{- with .Values.favorite }}
  drink: {{ .drink | default "tea" | quote }}
  food: {{ .food | upper | quote }}
  {{- end }}
  release: {{ .Release.Name }}
```
- Or, we can use `$` for accessing the object `Release.Name` from the parent scope. 
- `$` is mapped to the root scope when template execution begins and it does not change during template execution. 
- The following would work as well:
```yaml
  {{- with .Values.favorite }}
  drink: {{ .drink | default "tea" | quote }}
  food: {{ .food | upper | quote }}
  release: {{ $.Release.Name }}
  {{- end }}
```

- After looking at range, we will take a look at template variables, which offer one solution to the scoping issue above.

## [Looping with the range action](https://helm.sh/docs/chart_template_guide/control_structures/#looping-with-the-range-action)
- Many programming languages have support for looping using for loops, foreach loops, or similar functional mechanisms. 
- In Helm's template language, the way to iterate through a collection is to use the range operator.
- To start, let's add a list of pizza toppings to our values.yaml file:
```yaml
favorite:
  drink: coffee
  food: pizza
pizzaToppings:
  - mushrooms
  - cheese
  - peppers
  - onions
```
Now we have a list (called a slice in templates) of pizzaToppings. We can modify our template to print this list into our ConfigMap:

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  {{- with .Values.favorite }}
  drink: {{ .drink | default "tea" | quote }}
  food: {{ .food | upper | quote }}
  {{- end }}
  toppings: |-
    {{- range .Values.pizzaToppings }}
    - {{ . | title | quote }}
    {{- end }}    
```
We can use `$` for accessing the list Values.pizzaToppings from the parent scope. $ is mapped to the root scope when template execution begins and it does not change during template execution. The following would work as well:

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  {{- with .Values.favorite }}
  drink: {{ .drink | default "tea" | quote }}
  food: {{ .food | upper | quote }}
  toppings: |-
    {{- range $.Values.pizzaToppings }}
    - {{ . | title | quote }}
    {{- end }}    
  {{- end }}
```

- Let's take a closer look at the toppings: list. 
  - The range function will "range over" (iterate through) the pizzaToppings list. 
  - But now something interesting happens. 
  - Just like with sets the scope of `.`, so does a range operator. 
  - Each time through the loop, `.` is set to the current pizza topping.
    - That is, the first time, `.` is set to mushrooms. 
    - The second iteration it is set to cheese, and so on.

We can send the value of `.` directly down a pipeline, so when we do `{{ . | title | quote }}`, it sends `.` to title (title case function) and then to quote. If we run this template, the output will be:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: edgy-dragonfly-configmap
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "PIZZA"
  toppings: |-
    - "Mushrooms"
    - "Cheese"
    - "Peppers"
    - "Onions"    
```

Now, in this example we've done something tricky.
- The toppings: `|-` line is declaring a multi-line string. 
- So our list of toppings is actually not a YAML list. It's a big string. 
- Why would we do this? 
  - Because the data in ConfigMaps data is composed of key/value pairs, where both the key and the value are simple strings. 
  - To understand why this is the case, take a look at the Kubernetes ConfigMap docs. 
  - For us, though, this detail doesn't matter much.

- The `|-` marker in YAML takes a multi-line string. 
- This can be a useful technique for embedding big blocks of data inside of your manifests, as exemplified here.
- Sometimes it's useful to be able to quickly make a list inside of your template, and then iterate over that list. 
- Helm templates have a function to make this easy: `tuple`. 
- In computer science, a tuple is a list-like collection of fixed size, but with arbitrary data types. 
- This roughly conveys the way a tuple is used.
```yaml
  sizes: |-
    {{- range tuple "small" "medium" "large" }}
    - {{ . }}
    {{- end }}    
```

The above will produce this:
```yaml
  sizes: |-
    - small
    - medium
    - large    
```
In addition to lists and tuples, range can be used to iterate over collections that have a key and a value (like a map or dict). We'll see how to do that in the next section when we introduce template variables.

# Variables
With functions, pipelines, objects, and control structures under our belts, we can turn to one of the more basic ideas in many programming languages: `variables`. 
- In templates, they are less frequently used. 
- But we will see how to use them to simplify code, and to make better use of with and range.

In an earlier example, we saw that this code will fail:
```yaml
  {{- with .Values.favorite }}
  drink: {{ .drink | default "tea" | quote }}
  food: {{ .food | upper | quote }}
  release: {{ .Release.Name }}
  {{- end }}
```

- `Release.Name` is not inside of the scope that's restricted in the with block. 
- One way to work around scoping issues is to assign objects to variables that can be accessed without respect to the present scope. 
- In Helm templates, a variable is a named reference to another object. 
- It follows the form `$name`. 
- Variables are assigned with a special assignment operator: `:=`. 
- We can rewrite the above to use a variable for `Release.Name`.
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  {{- $relname := .Release.Name -}}
  {{- with .Values.favorite }}
  drink: {{ .drink | default "tea" | quote }}
  food: {{ .food | upper | quote }}
  release: {{ $relname }}
  {{- end }}
```

- Notice that before we start the with block, we assign `$relname := .Release.Name`. 
- Now inside of the with block, the `$relname` variable still points to the release name.

Running that will produce this:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: viable-badger-configmap
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "PIZZA"
  release: viable-badger
```

Variables are particularly useful in range loops. They can be used on list-like objects to capture both the index and the value
```yaml
  toppings: |-
    {{- range $index, $topping := .Values.pizzaToppings }}
      {{ $index }}: {{ $topping }}
    {{- end }}    
```

> Note that range comes first, then the variables, then the assignment operator, then the list. 

- This will assign the integer index (starting from zero) to $index and the value to $topping. 
- Running it will produce:
```yaml
  toppings: |-
      0: mushrooms
      1: cheese
      2: peppers
      3: onions      
```

For data structures that have both a key and a value, we can use range to get both. 
- For example, we can loop through .Values.favorite like this:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  {{- range $key, $val := .Values.favorite }}
  {{ $key }}: {{ $val | quote }}
  {{- end }}
```

Now on the first iteration, $key will be drink and $val will be coffee, and on the second, $key will be food and $val will be pizza. Running the above will generate this:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: eager-rabbit-configmap
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "pizza"
```

- Variables are normally not "global". 
- They are scoped to the block in which they are declared. 
- Earlier, we assigned `$relname` in the top level of the template. 
- That variable will be in scope for the entire template. 
- But in our last example, `$key` and `$val` will only be in scope inside of the `{{ range... }}{{ end }}` block.
- However, there is one variable that is always global - `$` - this variable will always point to the root context. 
- This can be very useful when you are looping in a range and you need to know the chart's release name.

An example illustrating this:
```yaml
{{- range .Values.tlsSecrets }}
apiVersion: v1
kind: Secret
metadata:
  name: {{ .name }}
  labels:
    # Many helm templates would use `.` below, but that will not work,
    # however `$` will work here
    app.kubernetes.io/name: {{ template "fullname" $ }}
    # I cannot reference .Chart.Name, but I can do $.Chart.Name
    helm.sh/chart: "{{ $.Chart.Name }}-{{ $.Chart.Version }}"
    app.kubernetes.io/instance: "{{ $.Release.Name }}"
    # Value from appVersion in Chart.yaml
    app.kubernetes.io/version: "{{ $.Chart.AppVersion }}"
    app.kubernetes.io/managed-by: "{{ $.Release.Service }}"
type: kubernetes.io/tls
data:
  tls.crt: {{ .certificate }}
  tls.key: {{ .key }}
---
{{- end }}
```
- So far we have looked at just one template declared in just one file. 
- But one of the powerful features of the Helm template language is its ability to declare multiple templates and use them together. 
- We'll turn to that in the next section.

# Named Templates
A named template (sometimes called a partial or a subtemplate) is simply a template defined inside of a file, and given a name. 
- We'll see two ways to create them, and a few different ways to use them.
- In the Flow Control section we introduced three actions for declaring and managing templates: `define`, `template`, and `block`. 
- In this section, we'll cover those three actions, and also introduce a special-purpose include function that works similarly to the template action.

An important detail to keep in mind when naming templates: template names are global
- If you declare two templates with the same name, whichever one is loaded last will be the one used. 
- Because templates in subcharts are compiled together with top-level templates, you should be careful to name your templates with chart-specific names.
- One popular naming convention is to prefix each defined template with the name of the chart: `{{ define "mychart.labels" }}`. 
- By using the specific chart name as a prefix we can avoid any conflicts that may arise due to two different charts that implement templates of the same name.

This behavior also applies to different versions of a chart. 
- If you have mychart version 1.0.0 that defines a template one way, and a mychart version 2.0.0 that modifies the existing named template, it will use the one that was loaded last. 
  - You can work around this issue by also adding a version in the name of the chart: `{{ define "mychart.v1.labels" }}` and `{{ define "mychart.v2.labels" }}`.

## Partials and _ files
So far, we've used one file, and that one file has contained a single template. 
- But Helm's template language allows you to create named embedded templates, that can be accessed by name elsewhere.
- Before we get to the nuts-and-bolts of writing those templates, there is file naming convention that deserves mention:

- Most files in templates/ are treated as if they contain Kubernetes manifests
  - The `NOTES.txt` is one exception
- But files whose name begins with an underscore (_) are assumed to not have a manifest inside. 
- These files are not rendered to Kubernetes object definitions, but are available everywhere within other chart templates for use.
- These files are used to store partials and helpers. 
- In fact, when we first created mychart, we saw a file called `_helpers.tpl`. 
- That file is the default location for template partials.

## Declaring and using templates with define and template
- The define action allows us to create a named template inside of a template file. 
- Its syntax goes like this:
```yaml
{{- define "MY.NAME" }}
  # body of template here
{{- end }}
```

For example, we can define a template to encapsulate a Kubernetes block of labels:
```yaml
{{- define "mychart.labels" }}
  labels:
    generator: helm
    date: {{ now | htmlDate }}
{{- end }}
```

Now we can embed this template inside of our existing ConfigMap, and then include it with the template action:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
  {{- template "mychart.labels" }}
data:
  myvalue: "Hello World"
  {{- range $key, $val := .Values.favorite }}
  {{ $key }}: {{ $val | quote }}
  {{- end }}
```
- When the template engine reads this file, it will store away the reference to `mychart.labels` until template `"mychart.labels"` is called. 
- Then it will render that template inline. 
- So the result will look like this:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: running-panda-configmap
  labels:
    generator: helm
    date: 2016-11-02
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "pizza"
```
> Note: a define does not produce output unless it is called with a template, as in this example.

- Conventionally, Helm charts put these templates inside of a partials file, usually `_helpers.tpl`. 

Let's move this function there:
```
{{/* Generate basic labels */}}
{{- define "mychart.labels" }}
  labels:
    generator: helm
    date: {{ now | htmlDate }}
{{- end }}
```

- By convention, `define functions` should have a simple documentation block `({{/* ... */}})` describing what they do.
- Even though this definition is in `_helpers.tpl`, it can still be accessed in `configmap.yaml`:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
  {{- template "mychart.labels" }}
data:
  myvalue: "Hello World"
  {{- range $key, $val := .Values.favorite }}
  {{ $key }}: {{ $val | quote }}
  {{- end }}
```

- As mentioned above, template names are global. 
- As a result of this, if two templates are declared with the same name the last occurrence will be the one that is used. 
- Since templates in subcharts are compiled together with top-level templates, it is best to name your templates with chart specific names. 
- A popular naming convention is to prefix each defined template with the name of the chart: `{{ define "mychart.labels" }}`.

## Setting the scope of a template
- In the template we defined above, we did not use any objects. 
- We just used functions. 
- Let's modify our defined template to include the chart name and chart version:
```yaml
{{/* Generate basic labels */}}
{{- define "mychart.labels" }}
  labels:
    generator: helm
    date: {{ now | htmlDate }}
    chart: {{ .Chart.Name }}
    version: {{ .Chart.Version }}
{{- end }}
```

If we render this, we will get an error like this:
```shell
$ helm install --dry-run moldy-jaguar ./mychart
Error: unable to build kubernetes objects from release manifest: error validating "": error validating data: [unknown object type "nil" in ConfigMap.metadata.labels.chart, unknown object type "nil" in ConfigMap.metadata.labels.version]
```

- To see what rendered, re-run with `--disable-openapi-validation`: 
```shell
helm install --dry-run --disable-openapi-validation moldy-jaguar ./mychart. 
```

The result will not be what we expect:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: moldy-jaguar-configmap
  labels:
    generator: helm
    date: 2021-03-06
    chart:
    version:
```

- What happened to the name and version? 
- They weren't in the scope for our defined template. 
- When a named template (created with define) is rendered, it will receive the scope passed in by the template call. 
- In our example, we included the template like this:
```yaml
{{- template "mychart.labels" }}
```

- No scope was passed in, so within the template we cannot access anything in `.`. 
- This is easy enough to fix, though. 
  - We simply pass a scope to the template:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
  {{- template "mychart.labels" . }}
```

- Note that we pass `.` at the end of the template call. 
- We could just as easily pass `.Values` or `.Values.favorite` or whatever scope we want. 
- But what we want is the top-level scope.

Now when we execute this template with 
```
helm install --dry-run --debug plinking-anaco ./mychart
```
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: plinking-anaco-configmap
  labels:
    generator: helm
    date: 2021-03-06
    chart: mychart
    version: 0.1.0
```

> Now `{{ .Chart.Name }}` resolves to mychart, and `{{ .Chart.Version }}` resolves to `0.1.0`.

## The include function
Say we've defined a simple template that looks like this:

```yaml
{{- define "mychart.app" -}}
app_name: {{ .Chart.Name }}
app_version: "{{ .Chart.Version }}"
{{- end -}}
```

Now say I want to insert this both into the `labels:` section of my template, and also the `data:` section:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
  labels:
    {{ template "mychart.app" . }}
data:
  myvalue: "Hello World"
  {{- range $key, $val := .Values.favorite }}
  {{ $key }}: {{ $val | quote }}
  {{- end }}
{{ template "mychart.app" . }}
```

If we render this, we will get an error like this:
```
$ helm install --dry-run measly-whippet ./mychart
Error: unable to build kubernetes objects from release manifest: error validating "": error validating data: [ValidationError(ConfigMap): unknown field "app_name" in io.k8s.api.core.v1.ConfigMap, ValidationError(ConfigMap): unknown field "app_version" in io.k8s.api.core.v1.ConfigMap]

```
To see what rendered, re-run with --disable-openapi-validation: 
```
helm install --dry-run --disable-openapi-validation measly-whippet ./mychart. 
```

The output will not be what we expect:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: measly-whippet-configmap
  labels:
    app_name: mychart
app_version: "0.1.0"
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "pizza"
app_name: mychart
app_version: "0.1.0"
```

- Note that the indentation on `app_version` is wrong in both places. 
  - Why? 
    - Because the template that is substituted in has the text aligned to the left. 
    - Because template is an action, and not a function, there is no way to pass the output of a template call to other functions; the data is simply inserted inline.
- To work around this case, Helm provides an alternative to template that will import the contents of a template into the present pipeline where it can be passed along to other functions in the pipeline.
- Here's the example above, corrected to use indent to indent the mychart.app template correctly:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
  labels:
{{ include "mychart.app" . | indent 4 }}
data:
  myvalue: "Hello World"
  {{- range $key, $val := .Values.favorite }}
  {{ $key }}: {{ $val | quote }}
  {{- end }}
{{ include "mychart.app" . | indent 2 }}
```

- Now the produced YAML is correctly indented for each section:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: edgy-mole-configmap
  labels:
    app_name: mychart
    app_version: "0.1.0"
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "pizza"
  app_name: mychart
  app_version: "0.1.0"
```

> It is considered preferable to use include over template in Helm templates simply so that the output formatting can be handled better for YAML documents.

- Sometimes we want to import content, but not as templates. 
  - That is, we want to import files verbatim. 
  - We can achieve this by accessing files through the `.Files` object described in the next section.

# [Accessing Files Inside Templates](https://helm.sh/docs/chart_template_guide/accessing_files/)
Helm provides access to files through the `.Files` object. 
- It is okay to add extra files to your Helm chart. 
- These files will be bundled.
- Be careful, though. Charts must be smaller than 1M because of the storage limitations of Kubernetes objects.
- Some files cannot be accessed through the `.Files` object, usually for security reasons.
  - Files in `templates/` cannot be accessed.
  - Files excluded using `.helmignore` cannot be accessed.
  - Files outside of a Helm application subchart, including those of the parent, cannot be accessed
  - Charts do not preserve UNIX mode information, so file-level permissions will have no impact on the availability of a file when it comes to the `.Files` object.

## Basic example
- With those caveats behind, let's write a template that reads three files into our ConfigMap. 
- To get started, we will add three files to the chart, putting all three directly inside of the `mychart/` directory.

`config1.toml`:
```
message = Hello from config 1
```

`config2.toml`:
```
message = This is config 2
```

`config3.toml`:
```
message = Goodbye from config 3
```

- Each of these is a simple TOML file (think old-school Windows INI files). 
- We know the names of these files, so we can use a range function to loop through them and inject their contents into our ConfigMap.
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  {{- $files := .Files }}
  {{- range tuple "config1.toml" "config2.toml" "config3.toml" }}
  {{ . }}: |-
        {{ $files.Get . }}
  {{- end }}
```

This ConfigMap uses several of the techniques discussed in previous sections.
- For example, we create a `$files` variable to hold a reference to the `.Files` object. 
- We also use the tuple function to create a list of files that we loop through. 
- Then we print each file name ({{ . }}: |-) followed by the contents of the file {{ $files.Get . }}.

Running this template will produce a single ConfigMap with the contents of all three files:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: quieting-giraf-configmap
data:
  config1.toml: |-
        message = Hello from config 1

  config2.toml: |-
        message = This is config 2

  config3.toml: |-
        message = Goodbye from config 3
```

## Path helpers
When working with files, it can be very useful to perform some standard operations on the file paths themselves. 
- To help with this, Helm imports many of the functions from Go's path package for your use. 
- They are all accessible with the same names as in the Go package, but with a lowercase first letter. 

## Glob patterns
As your chart grows, you may find you have a greater need to organize your files more, and so we provide a `Files.Glob(pattern string)` method to assist in extracting certain files with all the flexibility of glob patterns.
- `.Glob` returns a Files type, so you may call any of the Files methods on the returned object.

For example, imagine the directory structure:
```yaml
foo/:
  foo.txt foo.yaml

bar/:
  bar.go bar.conf baz.yaml
```
You have multiple options with Globs:
```yaml
{{ $currentScope := .}}
{{ range $path, $_ :=  .Files.Glob  "**.yaml" }}
    {{- with $currentScope}}
        {{ .Files.Get $path }}
    {{- end }}
{{ end }}
```
Or
```yaml
{{ range $path, $_ :=  .Files.Glob  "**.yaml" }}
      {{ $.Files.Get $path }}
{{ end }}
```

## ConfigMap and Secrets utility functions
It is very common to want to place file content into both ConfigMaps and Secrets, for mounting into your pods at run time. To help with this, we provide a couple utility methods on the Files type.

For further organization, it is especially useful to use these methods in conjunction with the Glob method.

Given the directory structure from the Glob example above:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: conf
data:
{{ (.Files.Glob "foo/*").AsConfig | indent 2 }}
---
apiVersion: v1
kind: Secret
metadata:
  name: very-secret
type: Opaque
data:
{{ (.Files.Glob "bar/*").AsSecrets | indent 2 }}
```

## Encoding
You can import a file and have the template base-64 encode it to ensure successful transmission:
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: {{ .Release.Name }}-secret
type: Opaque
data:
  token: |-
        {{ .Files.Get "config1.toml" | b64enc }}
```

The above will take the same config1.toml file we used before and encode it:
```yaml
# Source: mychart/templates/secret.yaml
apiVersion: v1
kind: Secret
metadata:
  name: lucky-turkey-secret
type: Opaque
data:
  token: |-
        bWVzc2FnZSA9IEhlbGxvIGZyb20gY29uZmlnIDEK
```

## Lines
Sometimes it is desirable to access each line of a file in your template. We provide a convenient Lines method for this.

You can loop through Lines using a range function:
```yaml
data:
  some-file.txt: {{ range .Files.Lines "foo/bar.txt" }}
    {{ . }}{{ end }}
```

> There is no way to pass files external to the chart during helm install. So if you are asking users to supply data, it must be loaded using helm install -f or helm install --set.

# [Creating a NOTES.txt File](https://helm.sh/docs/chart_template_guide/notes_files/)
- In this section we are going to look at Helm's tool for providing instructions to your chart users.
- At the end of a helm install or helm upgrade, Helm can print out a block of helpful information for users. 
- This information is highly customizable using templates.

- To add installation notes to your chart, simply create a `templates/NOTES.txt` file.
- This file is plain text, but it is processed like a template, and has all the normal template functions and objects available.

Let's create a simple NOTES.txt file:
```yaml
Thank you for installing {{ .Chart.Name }}.

Your release is named {{ .Release.Name }}.

To learn more about the release, try:

  $ helm status {{ .Release.Name }}
  $ helm get all {{ .Release.Name }}
```

Now if we run `helm install rude-cardinal ./mychart` we will see this message at the bottom:
```yaml
RESOURCES:
==> v1/Secret
NAME                   TYPE      DATA      AGE
rude-cardinal-secret   Opaque    1         0s

==> v1/ConfigMap
NAME                      DATA      AGE
rude-cardinal-configmap   3         0s


NOTES:
Thank you for installing mychart.

Your release is named rude-cardinal.

To learn more about the release, try:

  $ helm status rude-cardinal
  $ helm get all rude-cardinal
```

Using NOTES.txt this way is a great way to give your users detailed information about how to use their newly installed chart. Creating a NOTES.txt file is strongly recommended, though it is not required.

# Subcharts and Global Values
Charts can have dependencies, called `subcharts`, that also have their own values and templates. 
- Before we dive into the code, there are a few important details to learn about application subcharts.
  - A subchart can never depend on its parent chart, therefore a subchart cannot access values of its parent.
  - A parent chart can override values for subcharts.
- Helm has a concept of global values that can be accessed by all charts.
- These limitations do not all necessarily apply to [library charts](https://helm.sh/docs/topics/library_charts/), which are designed to provide standardized helper functionality.

## Creating a Subchart
For these exercises, we'll start with the `mychart/` chart we created at the beginning of this guide, and we'll add a new chart inside of it.
```shell
$ cd mychart/charts
$ helm create mysubchart
Creating mysubchart
$ rm -rf mysubchart/templates/*
```

> Notice that just as before, we deleted all of the base templates so that we can start from scratch. 

## Adding Values and a Template to the Subchart
- Next, let's create a simple template and values file for our mysubchart chart. 
- There should already be a `values.yaml` in `mychart/charts/mysubchart`.
- We'll set it up like this:
```yaml
dessert: cake
```

Next, we'll create a new ConfigMap template in `mychart/charts/mysubchart/templates/configmap.yaml`:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-cfgmap2
data:
  dessert: {{ .Values.dessert }}
```

Because every subchart is a stand-alone chart, we can test mysubchart on its own:
```yaml
$ helm install --generate-name --dry-run --debug mychart/charts/mysubchart
SERVER: "localhost:44134"
CHART PATH: /Users/mattbutcher/Code/Go/src/helm.sh/helm/_scratch/mychart/charts/mysubchart
NAME:   newbie-elk
TARGET NAMESPACE:   default
CHART:  mysubchart 0.1.0
MANIFEST:
---
# Source: mysubchart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: newbie-elk-cfgmap2
data:
  dessert: cake
```

## Overriding Values from a Parent Chart
Our original chart, mychart is now the parent chart of mysubchart. 
- This relationship is based entirely on the fact that mysubchart is within `mychart/charts`.

Because `mychart` is a parent, we can specify configuration in `mychart` and have that configuration pushed into `mysubchart`. 

For example, we can modify `mychart/values.yaml` like this:
```yaml
favorite:
  drink: coffee
  food: pizza
pizzaToppings:
  - mushrooms
  - cheese
  - peppers
  - onions

mysubchart:
  dessert: ice cream
```

> Note the last two lines. Any directives inside of the mysubchart section will be sent to the mysubchart chart. 

If we run `helm install --generate-name --dry-run --debug mychart`, one of the things we will see is the mysubchart ConfigMap:
```yaml
# Source: mychart/charts/mysubchart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: unhinged-bee-cfgmap2
data:
  dessert: ice cream
```

> The value at the top level has now overridden the value of the subchart.

- There's an important detail to notice here. 
  - We didn't change the template of `mychart/charts/mysubchart/templates/configmap.yaml` to point to `.Values.mysubchart.dessert`. 
  - From that template's perspective, the value is still located at `.Values.dessert`. 
  - As the template engine passes values along, it sets the scope. 
  - So for the mysubchart templates, only values specifically for mysubchart will be available in `.Values`.

Sometimes, though, you do want certain values to be available to all of the templates. This is accomplished using global chart values.

## Global Chart Values
Global values are values that can be accessed from any chart or subchart by exactly the same name. 
- Globals require explicit declaration. 
- You can't use an existing non-global as if it were a global.
- The `Values` data type has a reserved section called `Values.global` where global values can be set. 

Let's set one in our `mychart/values.yaml` file.
```yaml
favorite:
  drink: coffee
  food: pizza
pizzaToppings:
  - mushrooms
  - cheese
  - peppers
  - onions

mysubchart:
  dessert: ice cream

global:
  salad: caesar
```

Because of the way globals work, both `mychart/templates/configmap.yaml` and `mysubchart/templates/configmap.yaml` should be able to access that value as `{{ .Values.global.salad }}`.

`mychart/templates/configmap.yaml`:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  salad: {{ .Values.global.salad }}
mysubchart/templates/configmap.yaml:

apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-cfgmap2
data:
  dessert: {{ .Values.dessert }}
  salad: {{ .Values.global.salad }}
```

Now if we run a dry run install, we'll see the same value in both outputs:
```yaml
# Source: mychart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: silly-snake-configmap
data:
  salad: caesar

---
# Source: mychart/charts/mysubchart/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: silly-snake-cfgmap2
data:
  dessert: ice cream
  salad: caesar
```

Globals are useful for passing information like this, though it does take some planning to make sure the right templates are configured to use globals.

## Sharing Templates with Subcharts
Parent charts and subcharts can share templates. Any defined block in any chart is available to other charts.

For example, we can define a simple template like this:
```yaml
{{- define "labels" }}from: mychart{{ end }}
```

Recall how the labels on templates are globally shared. Thus, the labels chart can be included from any other chart.

While chart developers have a choice between include and template, one advantage of using include is that include can dynamically reference templates:
```yaml
{{ include $mytemplate }}
```

The above will dereference `$mytemplate`. The template function, in contrast, will only accept a string literal.

## Avoid Using Blocks
The Go template language provides a block keyword that allows developers to provide a default implementation which is overridden later. In Helm charts, blocks are not the best tool for overriding because if multiple implementations of the same block are provided, the one selected is unpredictable.

The suggestion is to instead use include.

# The .helmignore file
- The `.helmignore` file is used to specify files you don't want to include in your helm chart.
- If this file exists, the helm package command will ignore all the files that match the pattern specified in the `.helmignore` file while packaging your application.
  - This can help in avoiding unnecessary or sensitive files or directories from being added in your helm chart.
- The `.helmignore` file supports Unix shell glob matching, relative path matching, and negation (prefixed with !). 
- Only one pattern per line is considered.

Here is an example .helmignore file:
```yaml
# comment

# Match any file or path named .helmignore
.helmignore

# Match any file or path named .git
.git

# Match any text file
*.txt

# Match only directories named mydir
mydir/

# Match only text files in the top-level directory
/*.txt

# Match only the file foo.txt in the top-level directory
/foo.txt

# Match any file named ab.txt, ac.txt, or ad.txt
a[b-d].txt

# Match any file under subdir matching temp*
*/temp*

*/*/temp*
temp?
```
Some notable differences from .gitignore:

- The `**` syntax is not supported.
- The globbing library is Go's `filepath.Match`, not `fnmatch(3)`
- Trailing spaces are always ignored (there is no supported escape sequence)
- There is no support for `!` as a special leading sequence.
- It does not exclude itself by default, you have to add an explicit entry for `.helmignore`

We'd love your help making this document better. To add, correct, or remove information, file an issue or send us a pull request.

# Debugging Templates
Debugging templates can be tricky because the rendered templates are sent to the Kubernetes API server, which may reject the YAML files for reasons other than formatting.

There are a few commands that can help you debug.
- `helm lint` 
  - verify that your chart follows best practices
- `helm template --debug` 
  - test rendering chart templates locally.
- `helm install --dry-run --debug` 
  - render your chart locally without installing it
  - also check if conflicting resources are already running on the cluster. 
  - Setting `--dry-run=server` will additionally execute any lookup in your chart towards the server.
- `helm get manifest` 
  - see what templates are installed on the server

When your YAML is failing to parse, but you want to see what is generated, one easy way to retrieve the YAML is to comment out the problem section in the template, and then re-run `helm install --dry-run --debug`. This provides a quick way of viewing the generated content without YAML parse errors blocking.
```yaml
apiVersion: v2
# some: problem section
# {{ .Values.foo | quote }}
```

The above will be rendered and returned with the comments intact:
```yaml
apiVersion: v2
# some: problem section
#  "bar"
```

# Next Steps
This guide is intended to give you, the chart developer, a strong understanding of how to use Helm's template language. The guide focuses on the technical aspects of template development.

But there are many things this guide has not covered when it comes to the practical day-to-day development of charts. Here are some useful pointers to other documentation that will help you as you create new charts:

- The CNCF [Artifact Hub](https://artifacthub.io/packages/search?kind=0) is an indispensable source of charts.
- The [Kubernetes Documentation](https://kubernetes.io/docs/home/) provides detailed examples of the various resource kinds that you can use, from ConfigMaps and Secrets to DaemonSets and Deployments.
- The [Helm Charts Guide](https://helm.sh/docs/topics/charts/) explains the workflow of using charts.
- The [Helm Chart Hooks Guide](https://helm.sh/docs/topics/charts_hooks/) explains how to create lifecycle hooks.
- The [Helm Charts Tips and Tricks](https://helm.sh/docs/howto/charts_tips_and_tricks/) article provides some useful tips for writing charts.
- The [Sprig documentation](https://github.com/Masterminds/sprig) documents more than sixty of the template functions.
- The [Go template docs](https://godoc.org/text/template) explain the template syntax in detail.
- The [Schelm tool](https://github.com/databus23/schelm) is a nice helper utility for debugging charts.
- See [Appendix: YAML Techniques](https://helm.sh/docs/chart_template_guide/yaml_techniques/) for some useful YAML features
- See [Appendix: Go Data Types and Templates](https://helm.sh/docs/chart_template_guide/data_types/)
- See [Appendix: Go Data Types and Templates](https://helm.sh/docs/chart_template_guide/data_types/) to see Go data types used in templates

Sometimes it's easier to ask a few questions and get answers from experienced developers. The best place to do this is in the [Kubernetes Slack](https://kubernetes.slack.com/) Helm channels:
- `#helm-users`
- `#helm-dev`
- `#charts`

Finally, if you find errors or omissions in this document, want to suggest some new content, or would like to contribute, visit [The Helm Project](https://github.com/helm/helm-www).

