# EPUBCheck

[![Current Release](https://img.shields.io/github/release/w3c/epubcheck.svg)](https://github.com/w3c/epubcheck/releases/latest) [![Github All Releases Downloads](https://img.shields.io/github/downloads/w3c/epubcheck/total.svg?colorB=A9A9A9)](https://github.com/w3c/epubcheck/releases/) [![CI build with Maven](https://github.com/w3c/epubcheck/actions/workflows/maven-ci.yml/badge.svg)](https://github.com/w3c/epubcheck/actions/workflows/maven-ci.yml?query=branch%3Amain)

EPUBCheck is the official conformance checker for EPUB publications.
EPUBCheck can be run as a standalone command-line tool or used as a Java library.

EPUBCheck is open source software, maintained by the [DAISY Consortium](http://www.daisy.org) on behalf of [W3C](https://www.w3.org/publishing/epubcheck_fundraising).

**We Need Your Support!!**  
Financial support is critical to the development of EPUBCheck, the tool we all use to validate EPUB files.
We need to make sure that the resources are adequate to both update the tool and provide for its continued maintenance over the next two years;
please [help us fund and support EPUBCheck](https://www.w3.org/publishing/epubcheck_fundraising), and join the [list of donators](#donators)!

## Downloads

Check the [releases page](https://github.com/w3c/epubcheck/releases) to get the latest distribution.

[EPUBCheck v5.1.0](https://github.com/w3c/epubcheck/releases/tag/v5.1.0) is the latest production-ready release, to be used to validate both EPUB 2 and 3 files. EPUB 3 publications are checked against the [EPUB 3.3](https://www.w3.org/TR/epub-33/) specification.

## Documentation

Documentation on how to **use** EPUBCheck, to **contribute** to the project or to **translate** messages is available on the [EPUBCheck wiki](https://github.com/w3c/epubcheck/wiki).

Technical discussions are held on our public [mailing list](https://lists.w3.org/Archives/Public/public-epubcheck/). To subscribe to the mailing list, send an email with subject `subscribe` to [public-epubcheck-request@w3.org](mailto:public-epubcheck-request@w3.org?subject=subscribe). To participate in the discussion, simply send an email to [public-epubcheck@w3.org](mailto:public-epubcheck-request@w3.org).

Historical archives of discussions prior to October 2017 are stored at the old [EPUBCheck Google Group](https://groups.google.com/forum/#!forum/epubcheck).

## Building EPUBCheck

### Build from sources

To build epubcheck from the sources you need Java Development Kit (JDK) 1.7 or above and [Apache Maven](http://maven.apache.org/) 3.0 or above installed.

Build and run tests:

```bash
mvn clean install
```

Will copy `*.jar` files and packages to `target/` folder...

### Build using docker

To build the epubcheck using docker, use the build command below:

```bash
docker build . -t epubcheck
```

To run the epubcheck image as container, use example command below:

```bash
# one directory in the host need to be mapped (using docker volume) to /data path
# within container. the particular path will be used as a bridge to enable access
# over the epub file or the generated output file between host and container.
$ docker run -it --rm -v <directory>:/data epubcheck --help
$ docker run -it --rm -v <directory>:/data epubcheck <epub-file> [OPTIONS]

# example 1:
# execute an epub check over a file located in /home/username/file.epub on the host.
# the output will be printed to the console
$ docker run -it --rm -v /home/username:/data epubcheck file.epub

# example 2:
# execute an epub check over a file, and then generate an output file
# in /data/output.json within container.
# since /data is mapped via volume, then the generated file will be accessible
# from /home/username/output.json in the host
$ docker run - --rm -v /home/username:/data epubcheck file.epub --json output.json
```

## Credits

EPUBCheck v5.1.0 was developed by [the DAISY Consortium](https://www.daisy.org/), on behalf of W3C.

Initial EPUBCheck development was largely done at [Adobe](https://www.adobe.com/).
A significant part of EPUBCheck functionality comes from the schema validation tool [Jing](https://relaxng.org/jclark/jing.html), used with schemas from the [Nu HTML Checker](https://validator.github.io/validator/), [IDPF](https://idpf.org), and [DAISY](https://www.daisy.org/).

Past and present EPUBCheck developers include:
Romain Deltour, Matt Garrish, Tobias Fischer, Markus Gylling, Steve Antoch, Peter Sorotokin, Thomas Ledoux, Masayoshi Takahashi, Paul Norton, Piotr Kula, Arwen Pond, Liza Daly, Garth Conboy, and [several others](https://github.com/w3c/epubcheck/graphs/contributors).

Many thanks to the numerous people who have contributed to the evolution of EPUBCheck through bug reports, pull requests, and translations!

## Donators

The following organizations are supporting the development of EPUBCheck by their contribution to the [fundraising initiative](https://www.w3.org/publishing/epubcheck_fundraising):

![MacMillan Learning](https://www.w3.org/publishing/donators_logos/MacLearn_logo_cmyk.png){:width="200" style="margin-right: 20px;"}
![Google](https://www.w3.org/publishing/donators_logos/Google.png){:width="400" style="margin-right: 20px;"}
![DAISY](https://www.w3.org/publishing/donators_logos/daisy_high.jpg){:width="100" style="margin-right: 20px;"}
![Publizon A/S](https://www.w3.org/publishing/donators_logos/publizon-logo.jpg){:width="100" style="margin-right: 20px;"}
![Wiley](https://www.w3.org/publishing/donators_logos/Wiley_Wordmark_black.png){:width="200" style="margin-right: 20px;"}
![Hachette Livre](https://www.w3.org/publishing/donators_logos/Hachette%20Livre.jpg){:width="300" style="margin-right: 20px;"}
![LearningMate Solutions Inc](https://www.w3.org/publishing/donators_logos/LearningMate%20Logo.png){:width="100" style="margin-right: 20px;"}
![Voyager Japan, Inc.](https://www.w3.org/publishing/donators_logos/rectangle_VJstar_logo_512.jpg){:width="100" style="margin-right: 20px;"}
![QA Info Tech](https://www.w3.org/publishing/donators_logos/QA%20InfoTech%20Logo%20PNG%20Format.png){:width="200" style="margin-right: 20px;"}
![W. W. Norton](https://www.w3.org/publishing/donators_logos/NortonLogo_notagline.jpg){:width="100" style="margin-right: 20px;"}
![Lumina Datamatics, Inc.](https://www.w3.org/publishing/donators_logos/Datamatics_logo.jpg){:width="100" style="margin-right: 20px;"}
![Harper Collins](https://www.w3.org/publishing/donators_logos/HarperCollins.png){:width="200" style="margin-right: 20px;"}
![Vital Source](<https://www.w3.org/publishing/donators_logos/VS_Logo_HOR_Ingram_Tag(RGB).jpg>){:width="300" style="margin-right: 20px;"}
![Verlag C.H. Beck oHG](https://www.w3.org/publishing/donators_logos/Beck_LogoVektor_sw.jpg){:width="100" style="margin-right: 20px;"}
![Libreka](https://www.w3.org/publishing/donators_logos/logo_libreka.png){:width="100" style="margin-right: 20px;"}
![Zeilenwert](https://www.w3.org/publishing/donators_logos/logo_zeilenwert.jpg){:width="100" style="margin-right: 20px;"}
![Cenveo Publisher Services](https://www.w3.org/publishing/donators_logos/CVO%20Pub%20Serv_Logo.jpg){:width="100" style="margin-right: 20px;"}
![BookNet Canada](https://www.w3.org/publishing/donators_logos/BNC_Logo_Horizontal_RGB_1000px.png){:width="100" style="margin-right: 20px;"}

## License

EPUBCheck is made available under the terms of the [3-Clause BSD License](http://opensource.org/licenses/BSD-3-Clause)
