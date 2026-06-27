# jxlab
A laboratory of Java and JavaFX extensions oriented towards quick application boilerplate and import/export capabilities. Biased towards light science foundations, core graphical design elements, and acoustical applications, including signal processing. Intended also to support use in Matlab based workflows. 

This is a compilation of libraries in two halves: libraries that build upon core Java, and those that additionally depend on JavaFX. As it is easier to do related development in one workspace or project, they are not split at this level of repository organization. Most of the components were previously separate repositories, which became difficult to work with and also meant each super-jar had to be created for the machine that the overall set of repositories was downloaded to. Now we can have a super-jar.

As the previous repositories were too fine-tuned in purpose for it to be easy to see how they work as a whole, there has been consolidation such that the only real topical division anymore is between the more common coverage for i/o, networking, etc., math (though this could easily be folded into commons), physics, and signal processing (which is as much electrical engineering as it is physics, so it is a separate library). Additionally, there are several import/export capabilities in extra libraries.

Format support for Office, DXF, SVG, etc., generally requires many extra third-party libraries to be pulled in, so those remain separate builds and JAR files but now at least they can all be easily worked on together via a combined repository fetch. No one is obligated to build everything in the repository. 

The goal is to publish soon, so that only people intending to modify or extend these libraries need fetch the jxlab repository, and so that one can just pull or reference (via a Maven POM file) the JAR files that one needs.

This consolidation of prior libraries also involves a re-think about best organization and structure for where things go, which was additionally mandated by the upgrade from Java 8 to Java 25, as module files expose unnoticed cyclical dependencies and/or unfortunate dependency hierarchies that were not what was intended. We do not have time for a migration guide at this time.

The code was stuck at Java 8 for many years due to government contracting work, which often targets software for old hardware systems or ancient frameworks that have not yet moved past Java 8, Java 7, or in some cases even Java 6. Due to trends towards containerization, this restriction has recently lifted and we are now allowed to build the Java and JavaFX JAR files into our own distributions of libraries rather than being captive to a system-level Java installation.

The reason for jumping all the way to Java 25 is that we need the latest features that enhance the ability to control and observe calls to external non-Java applications in complex scientific visualization workflows and environments. As these requirements are all the way at the bottom of the dependency hierarchy in the commons library, everything is now Java 25.

We will do our best to pull in the older README files and high-level documentation of the consolidated libraries as part of the write-up of the new structure of top-level libraries within this newly consolidated repository.

A few of the libraries have temporary disablement of features while we look for ways to replace code (and libraries) that previously depended indirectly (via third-party libraries) on Private API that is not available for use past Java 8.
