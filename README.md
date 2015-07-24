A test case for tycho-packaging-plugin + builnumber-maven-plugin
================================================================

This is a minimal test case written for investigating an issue with
`tycho-packaging-plugin` and `buildnumber-maven-plugin`.

Test case succeeds with Tycho 0.22.0, but fails with 0.23.0 or higher.

The problem appears to be the order in which goals of
`tycho-packaging-plugin` and `buildnumber-maven-plugin` are executed
during validation phase: Since `buildnumber-maven-plugin` is declared
first in the POM, it would be expected to be executed first, as stated
in
[this page](https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html)
and as [a bug fix](https://issues.apache.org/jira/browse/MNG-2258)
should have made it effective in Maven 3.0.3.
