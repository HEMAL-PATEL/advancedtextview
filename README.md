# AdvancedTextview
[ ![Download](https://api.bintray.com/packages/ayar/maven/advancedtextview/images/download.svg) ](https://bintray.com/ayar/maven/advancedtextview/_latestVersion)

AdvancedTextView provides advanced features that simplifies complicated UI processes.

There are 5 main feaures (for now):

* [Justified Text Alignment](#justified-text-alignment)
* [Custom Fonts](#custom-fonts)
* [Expandable Text Layout](#expandable-text-layout)
* [AutoFit Text](#autofit-text)
* [Counting Text](#counting-text)

**Feature recommendations/requests are pleasedly welcomed**

**Note: This features works with only plain text. You cannot use AdvancedTextView with Spanned Text (for now)**

## Version Notes

#### 0.4.6
* Minor bugfixes

#### 0.4.5
* onExpandTextClickListener added to Expandable Layout

#### 0.4.1
* Detected bugs have been fixed

#### 0.4.0
* Counting text feature has been added

#### 0.3.5
* Detected bugs have been fixed

#### 0.3.0
Features/Attributes below have been added to Expanding Text Layout

* expandTextPosition
* expandTextSize
* expandText_margin (left, right, top, bottom)
* expandEllipsize


## Installation

### Maven

    <dependency>
		<groupId>ayar.oktay.library</groupId>
		<artifactId>advancedtextview</artifactId>
		<version>0.5.0</version>
		<type>pom</type>
	</dependency>

### Gradle

    compile 'ayar.oktay.library:advancedtextview:0.5.0'
### Ivy

    <dependency org='ayar.oktay.library' name='advancedtextview' rev='0.5.0'>
	  <artifact name='$AID' ext='pom'></artifact>
	</dependency>

## Features

### Justified Text Alignment

You can use justified text alignment simply by adding one attribute to your xml file

<img src="/arts/justifytext_ss.png" width="35%" height="35%" />

#### XML File

    <ayar.oktay.advancedtextview.AdvancedTextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/very_long_text"
            app:justifyText="true"
            />

### Custom Fonts

You can use custom fonts with AdvancedTextview. 

Fonts listed below are available to use without loading .ttf file. 



![Aller](/arts/aller.png)

![Bebas](/arts/bebas.png)

![Capture It](/arts/capture.png)

![Caviar Dreams](/arts/caviar_dreams.png)

![Droid Sans](/arts/droid_sans.png)

![Journal](/arts/journal.png)

![Open Sans](/arts/open_sans.png)

![Pacifico](/arts/pacifico.png)

![Roboto](/arts/roboto.png)




You can use any of them by declaring in your xml file.

    <ayar.oktay.advancedtextview.AdvancedTextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/very_long_text"
        app:typeFace="roboto_regular"
        />


You can also load .ttf file from assets folder by declaring in your xml file.

    <ayar.oktay.advancedtextview.AdvancedTextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginBottom="8dp"
        android:text="@string/very_long_text"
        app:fontFile="path_to_your_font_file"
        />

### Expandable Text Layout

AdvancedTextView provides expandable layout for long texts. You can use this feature with **ExpandableTextLayout**.
 `expandable`, `android:maxLines` and `expandText` must be set for expandable feature.

<img src="/arts/expandtext_ss1.png" width="35%" height="35%" />


<img src="/arts/expandtext_ss2.png" width="35%" height="35%" />

#### Attributes

* expandable (boolean): Enables/Disables expandable feature
* expandText (String): Text which is shown for expanding layout
* expandTextColor (coloe): expandText color (Default is #C5C5C5)
* expandTextPosition (enum): Determines alignment option of expandText according to its expanding text. left, center or right is accepted for this attribute
* expandTextSize (dimension): Determines size of expandText. Default is same dimension with expanding text
* expandEllipsize (boolean): Enables/Disables ellipsize at the end of the expanding text (default is true)
* expandText_margin (dimension): Determines margin according to expanding text of expandText for 4 sides (right, left, top and bottom)
* expandText_marginLeft (dimension): Determines left margin according to expanding text of expandText
* expandText_marginRight (dimension): Determines right margin according to expanding text of expandText
* expandText_marginTop (dimension): Determines top margin according to expanding text of expandText
* expandText_marginBottom (dimension): Determines bottom margin according to expanding text of expandText

**Only text can be used as expand widget. Other expand widgets such as Button, ImageButton will be added soon.**

**You cannot use this feature without using AdvancedTexview as child of ExpandableTextLayout.**

### AutoFit Text

You can fit your your texts into determined lines. You must set `autoFit` and `android:maxLines`  to use this feature.  You can also set minTextSize to determine minimum text size for auto fit process (Default is 6dp).

<img src="/arts/autofit_ss.png" width="50%" height="50%" />


    <ayar.oktay.advancedtextview.AdvancedTextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:maxLines="3"
        android:text="@string/long_text"
        app:autoFit="true"
        app:minTextSize="10dp"
        />
###Counting Text
You can demonstrate counting process from start value to end value. 

<img src="/arts/counting_text_demo.gif" width="25%" height="25%" />

#### Attributes

* coutingText (boolean): Enables/Disables counting text feature
* coutingText_startValue (integer): Determines start value of counting text (Default value is 0)
* coutingText_endValue (integer): Determines start value of counting text, **Must be assigned**
* coutingText_increment (integer): Determines increment value of every counting step (Default value is 10)
* coutingText_format (enum): Determines number format of text. It has 5 options, these options are **none**, **comma**, **commaWithZero**, **dot**, **dotWithZero**. You can see examples from demo above.
 
**Note: You cannot use counting text feature with Justified Text Alignment, Expandable Text Layout or AutoFit Text**


## Usage with Styles

You can set attributes for entire project/application by setting them in styles.

    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
    <!-- Customize your theme here. -->
    <item name="typeFace">roboto_regular</item>
    <item name="justifyText">true</item>
    <item name="autoFit">true</item>
    <item name="android:maxLines">5</item>
  </style>


## License

                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

      "Licensor" shall mean the copyright owner or entity authorized by
      the copyright owner that is granting the License.

      "Legal Entity" shall mean the union of the acting entity and all
      other entities that control, are controlled by, or are under common
      control with that entity. For the purposes of this definition,
      "control" means (i) the power, direct or indirect, to cause the
      direction or management of such entity, whether by contract or
      otherwise, or (ii) ownership of fifty percent (50%) or more of the
      outstanding shares, or (iii) beneficial ownership of such entity.

      "You" (or "Your") shall mean an individual or Legal Entity
      exercising permissions granted by this License.

      "Source" form shall mean the preferred form for making modifications,
      including but not limited to software source code, documentation
      source, and configuration files.

      "Object" form shall mean any form resulting from mechanical
      transformation or translation of a Source form, including but
      not limited to compiled object code, generated documentation,
      and conversions to other media types.

      "Work" shall mean the work of authorship, whether in Source or
      Object form, made available under the License, as indicated by a
      copyright notice that is included in or attached to the work
      (an example is provided in the Appendix below).

      "Derivative Works" shall mean any work, whether in Source or Object
      form, that is based on (or derived from) the Work and for which the
      editorial revisions, annotations, elaborations, or other modifications
      represent, as a whole, an original work of authorship. For the purposes
      of this License, Derivative Works shall not include works that remain
      separable from, or merely link (or bind by name) to the interfaces of,
      the Work and Derivative Works thereof.

      "Contribution" shall mean any work of authorship, including
      the original version of the Work and any modifications or additions
      to that Work or Derivative Works thereof, that is intentionally
      submitted to Licensor for inclusion in the Work by the copyright owner
      or by an individual or Legal Entity authorized to submit on behalf of
      the copyright owner. For the purposes of this definition, "submitted"
      means any form of electronic, verbal, or written communication sent
      to the Licensor or its representatives, including but not limited to
      communication on electronic mailing lists, source code control systems,
      and issue tracking systems that are managed by, or on behalf of, the
      Licensor for the purpose of discussing and improving the Work, but
      excluding communication that is conspicuously marked or otherwise
      designated in writing by the copyright owner as "Not a Contribution."

      "Contributor" shall mean Licensor and any individual or Legal Entity
      on behalf of whom a Contribution has been received by Licensor and
      subsequently incorporated within the Work.

   2. Grant of Copyright License. Subject to the terms and conditions of
      this License, each Contributor hereby grants to You a perpetual,
      worldwide, non-exclusive, no-charge, royalty-free, irrevocable
      copyright license to reproduce, prepare Derivative Works of,
      publicly display, publicly perform, sublicense, and distribute the
      Work and such Derivative Works in Source or Object form.

   3. Grant of Patent License. Subject to the terms and conditions of
      this License, each Contributor hereby grants to You a perpetual,
      worldwide, non-exclusive, no-charge, royalty-free, irrevocable
      (except as stated in this section) patent license to make, have made,
      use, offer to sell, sell, import, and otherwise transfer the Work,
      where such license applies only to those patent claims licensable
      by such Contributor that are necessarily infringed by their
      Contribution(s) alone or by combination of their Contribution(s)
      with the Work to which such Contribution(s) was submitted. If You
      institute patent litigation against any entity (including a
      cross-claim or counterclaim in a lawsuit) alleging that the Work
      or a Contribution incorporated within the Work constitutes direct
      or contributory patent infringement, then any patent licenses
      granted to You under this License for that Work shall terminate
      as of the date such litigation is filed.

   4. Redistribution. You may reproduce and distribute copies of the
      Work or Derivative Works thereof in any medium, with or without
      modifications, and in Source or Object form, provided that You
      meet the following conditions:

      (a) You must give any other recipients of the Work or
          Derivative Works a copy of this License; and

      (b) You must cause any modified files to carry prominent notices
          stating that You changed the files; and

      (c) You must retain, in the Source form of any Derivative Works
          that You distribute, all copyright, patent, trademark, and
          attribution notices from the Source form of the Work,
          excluding those notices that do not pertain to any part of
          the Derivative Works; and

      (d) If the Work includes a "NOTICE" text file as part of its
          distribution, then any Derivative Works that You distribute must
          include a readable copy of the attribution notices contained
          within such NOTICE file, excluding those notices that do not
          pertain to any part of the Derivative Works, in at least one
          of the following places: within a NOTICE text file distributed
          as part of the Derivative Works; within the Source form or
          documentation, if provided along with the Derivative Works; or,
          within a display generated by the Derivative Works, if and
          wherever such third-party notices normally appear. The contents
          of the NOTICE file are for informational purposes only and
          do not modify the License. You may add Your own attribution
          notices within Derivative Works that You distribute, alongside
          or as an addendum to the NOTICE text from the Work, provided
          that such additional attribution notices cannot be construed
          as modifying the License.

      You may add Your own copyright statement to Your modifications and
      may provide additional or different license terms and conditions
      for use, reproduction, or distribution of Your modifications, or
      for any such Derivative Works as a whole, provided Your use,
      reproduction, and distribution of the Work otherwise complies with
      the conditions stated in this License.

   5. Submission of Contributions. Unless You explicitly state otherwise,
      any Contribution intentionally submitted for inclusion in the Work
      by You to the Licensor shall be under the terms and conditions of
      this License, without any additional terms or conditions.
      Notwithstanding the above, nothing herein shall supersede or modify
      the terms of any separate license agreement you may have executed
      with Licensor regarding such Contributions.

   6. Trademarks. This License does not grant permission to use the trade
      names, trademarks, service marks, or product names of the Licensor,
      except as required for reasonable and customary use in describing the
      origin of the Work and reproducing the content of the NOTICE file.

   7. Disclaimer of Warranty. Unless required by applicable law or
      agreed to in writing, Licensor provides the Work (and each
      Contributor provides its Contributions) on an "AS IS" BASIS,
      WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or
      implied, including, without limitation, any warranties or conditions
      of TITLE, NON-INFRINGEMENT, MERCHANTABILITY, or FITNESS FOR A
      PARTICULAR PURPOSE. You are solely responsible for determining the
      appropriateness of using or redistributing the Work and assume any
      risks associated with Your exercise of permissions under this License.

   8. Limitation of Liability. In no event and under no legal theory,
      whether in tort (including negligence), contract, or otherwise,
      unless required by applicable law (such as deliberate and grossly
      negligent acts) or agreed to in writing, shall any Contributor be
      liable to You for damages, including any direct, indirect, special,
      incidental, or consequential damages of any character arising as a
      result of this License or out of the use or inability to use the
      Work (including but not limited to damages for loss of goodwill,
      work stoppage, computer failure or malfunction, or any and all
      other commercial damages or losses), even if such Contributor
      has been advised of the possibility of such damages.

   9. Accepting Warranty or Additional Liability. While redistributing
      the Work or Derivative Works thereof, You may choose to offer,
      and charge a fee for, acceptance of support, warranty, indemnity,
      or other liability obligations and/or rights consistent with this
      License. However, in accepting such obligations, You may act only
      on Your own behalf and on Your sole responsibility, not on behalf
      of any other Contributor, and only if You agree to indemnify,
      defend, and hold each Contributor harmless for any liability
      incurred by, or claims asserted against, such Contributor by reason
      of your accepting any such warranty or additional liability.

   END OF TERMS AND CONDITIONS

   APPENDIX: How to apply the Apache License to your work.

      To apply the Apache License to your work, attach the following
      boilerplate notice, with the fields enclosed by brackets "{}"
      replaced with your own identifying information. (Don't include
      the brackets!)  The text should be enclosed in the appropriate
      comment syntax for the file format. We also recommend that a
      file or class name and description of purpose be included on the
      same "printed page" as the copyright notice for easier
      identification within third-party archives.

   Copyright {2018} {Oktay AYAR}

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
