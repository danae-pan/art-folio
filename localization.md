---
layout: default
title: Localization
permalink: /localization/
---

<section class="section-heading">
  <p class="eyebrow">Visual Novel Localization</p>
  <h1>Wataju: My Super Fulfilling Real Life!</h1>
  <p>English Localization · Image Editing · UI Adaptation · Technical Implementation</p>
</section>


<!-- PROJECT OVERVIEW -->

<section class="project-block">
  <h2>Project Overview</h2>

  <p class="project-description">
    An ongoing personal English localization project for the freeware Japanese
    visual novel <em>Watashi no Real wa Juujitsu Shisugiteiru (Wataju)</em>.
  </p>

  <p class="project-description">
    The project combines dialogue localization with script implementation,
    image editing, UI adaptation, technical problem-solving, and in-game testing.
    My goal is to adapt the game for English while preserving the presentation,
    functionality, and visual identity of the original release.
  </p>

  <p class="project-description">
    The game was originally developed with NScripter, so the localization also
    involves working directly with its existing scripts and assets and adapting
    parts of the original implementation where Japanese-specific behavior does
    not translate directly to English.
  </p>
</section>


<!-- TECHNICAL IMPLEMENTATION -->

<section class="project-section">
  <h2>Technical Implementation & Challenges</h2>

  <section class="project-block">
    <h3>Working with the Original Game</h3>

    <p class="project-description">
      I extracted the original NScripter script and asset archive to identify
      which content could be localized through code and which text was embedded
      directly into graphical assets. The original script uses Shift-JIS / CP932,
      which is preserved throughout the current localization workflow.
    </p>

    <p class="project-description">
      During development, I found that the engine can load loose scripts and
      assets before their archived versions. I use this to test localization
      changes directly in-game without rebuilding the original archives after
      every edit.
    </p>
  </section>


  <section class="project-block">
    <h3>Adapting the Runtime for English</h3>

    <p class="project-description">
      The original runtime presented problems with English spacing, punctuation,
      and text rendering. To preserve the existing game structure while improving
      English text support, I created a separate testing environment using
      ONScripter-EN.
    </p>

    <p class="project-description">
        Moving the project to ONScripter-EN also came with a few compatibility issues.
        While the localized name-entry system works as expected in the original
        NScripter runtime, the same input field remains clickable in ONScripter-EN
        but does not accept keyboard input. Testing the same script in both runtimes
        helped narrow the issue down to how text input is handled by the engine.
    </p>
  </section>


  <section class="project-block">
    <h3>Dialogue & Script Implementation</h3>

    <p class="project-description">
      Localizing the dialogue requires more than replacing the original text.
      Existing script commands control speaker names, character colors, dynamic
      variables, scene progression, and click behavior, all of which need to
      remain functional around the English dialogue.
    </p>

    <p class="project-description">
      During testing, I identified and resolved issues caused by English
      punctuation and formatting being interpreted as script syntax, as well as
      inconsistencies in dialogue colors and dynamically displayed character
      names.
    </p>
  </section>
</section>


<!-- IMAGE EDITING -->

<section class="project-section">
  <h2>Image Editing & UI Localization</h2>

  <section class="project-block">
    <h3>Localizing Baked-In UI</h3>

    <p class="project-description">
      Some of the game's Japanese interface text is embedded directly into image
      assets rather than stored in the script. These elements have to be manually
      reconstructed and edited while preserving the artwork, colors, layout, and
      visual style of the original interface.
    </p>

     <p class="project-description">
        All images were editing using Clip Studio Paint software.
    </p>
  </section>


  <section class="project-block">
    <h3>Name Entry Screen</h3>

    <p class="project-description">
      The protagonist's name-entry screen became the first complete UI
      localization case study. The original screen was designed around Japanese
      full-width characters and contained both baked-in text and dynamically
      rendered elements.
    </p>

    <p class="project-description">
      I recreated the Japanese labels in English, matched the typography to the
      game's runtime font, edited the different button states, and redesigned the
      input area to accommodate the longer English labels without changing the
      overall visual identity of the screen.
    </p>

   

        <!-- NAME SCREEN COMPARISON -->

    <div class="comparison-grid">

      <div class="comparison-item">
        <h4>Original</h4>

        <img
          src="{{ '/assets/images/name_original.jpg' | relative_url }}"
          alt="Original Japanese name entry interface">
      </div>

      <div class="comparison-item">
        <h4>Localized</h4>

        <img
          src="{{ '/assets/images/name.jpg' | relative_url }}"
          alt="Localized English name entry interface">
      </div>

    </div>



 <!-- FONT -->

    <p class="project-description">
      To keep the localized interface consistent with the original game, I also
      investigated which font the game uses at runtime. The font was not defined
      directly in the script, so I inspected the game's environment data and
      identified it as MS Gothic. I then used the same typeface for the English UI
      element so that the edited graphics match the text rendered dynamically by
      the game.
    </p>


    <!-- INPUT FIELD -->

    <p class="project-description">
      The original input field also needed to be resized to create more room for
      the longer English labels. Rather than scaling the entire graphic, I edited
      its individual sprite states and reduced their width while preserving the
      original border thickness and proportions.
    </p>

    <div class="comparison-grid">

      <div class="comparison-item">
        <h4>Original Input Field</h4>

        <img
          class="asset-preview"
          src="{{ '/assets/images/input_original.png' | relative_url }}"
          alt="Original name input field">
      </div>

      <div class="comparison-item">
        <h4>Localized Input Field</h4>

        <img
          class="asset-preview"
          src="{{ '/assets/images/input.png' | relative_url }}"
          alt="Localized English name input field">
      </div>

    </div>


    <!-- ENTER BUTTON -->

    <p class="project-description">
      The confirmation button contains two sprite states for its normal
      and interactive appearance. Both states were edited so that the localized
      text remains consistent when the player interacts with the button.
    </p>

    <div class="comparison-grid">

      <div class="comparison-item">
        <h4>Original Button</h4>

        <img
          class="asset-preview"
          src="{{ '/assets/images/enter_original.png' | relative_url }}"
          alt="Original Japanese confirmation button">
      </div>

      <div class="comparison-item">
        <h4>Localized Button</h4>

        <img
          class="asset-preview"
          src="{{ '/assets/images/enter.png' | relative_url }}"
          alt="Localized English confirmation button">
      </div>

    </div>

  </section>


 <!-- NAME SYSTEM -->

  <section class="project-block">
    <h3>Adapting the Name System</h3>

    <p class="project-description">
      The visual changes also required modifications to the underlying script.
      The original input field accepted full-width Japanese characters and was
      designed around a five-character name limit.
    </p>

    <p class="project-description">
      I adapted the field to accept standard ASCII input, introduced an
      eight-character English limit, localized the validation message and
      default protagonist name, and repositioned the input field and dynamically
      rendered text to match the redesigned interface.
    </p>
  </section>


<!-- FINAL NAME SCREEN VIDEO -->

    <h3>Localized Name Entry in Game</h3>

    <p class="project-description">
      The final screen combines the localized graphical assets with the modified
      name-input system and is tested directly in-game to ensure that the visual
      and interactive elements work together correctly.
    </p>

    <!--
    Replace the filename below with your final video filename.
    -->

    <video controls muted loop playsinline class="project-video">
      <source
        src="{{ '/assets/videos/wataju-name-screen.mp4' | relative_url }}"
        type="video/mp4">
    </video>



</section>

<!-- TRANSLATION -->

<section class="project-section">
  <h2>Translation & Localization Process</h2>

  <section class="project-block">
    <p class="project-description">
      As I do not speak Japanese, I use translation tools to establish an initial
      interpretation of the source text and then work from the scene context to
      adapt it into natural English.
    </p>

    <p class="project-description">
        I translate each scene with its full context in mind, paying attention to
        character voice, dialogue flow, and how the lines feel when played in-game.
        After implementing the English text, I play through the scene again to check
        the dialogue, formatting, and overall presentation, making adjustments where needed.
    </p>
  </section>



    <!-- GAMEPLAY VIDEO -->

    <h3>English Dialogue In-Game</h3>

    <p class="project-description">
      Localized scenes are tested as part of the game rather than only reviewing
      the translated script. This makes it possible to check how the dialogue
      reads alongside character expressions, scene transitions, timing, and the
      rest of the game's presentation.
    </p>

    <!--
    Replace the filename below with your gameplay video filename.
    -->

    <video controls muted loop playsinline class="project-video">
      <source
        src="{{ '/assets/videos/wataju-localized-gameplay.mp4' | relative_url }}"
        type="video/mp4">
    </video>

  </section>

