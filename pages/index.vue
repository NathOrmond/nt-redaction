<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">New Testament Redaction Calculator</h1>
      <div class="about-text">
        <p class="paragraph">
          How do readers respond to pluriform texts and traditions? The first
          two centuries of the common era knew a dozen overlapping,
          complimentary, and conflicting lives of Jesus. My dissertation,
          “Rewriting the Gospels: The Synoptic Tradition in the First and Second
          Centuries,” situates these competing versions of Jesus’ life in
          Hellenistic and Roman book culture. Although treatments of “genre”
          abound, scholars have not discussed the gospels alongside other
          pluriform text traditions. Ancient readers had language for such
          overlapping, interdependent books, and this language shaped the
          composition and earliest reception of the gospels.
        </p>
        <p class="paragraph">
          I am applying for the Julian Price Graduate Fellowship to pay for the
          development of a modified Damerau-Levenshtein distance calculator. In
          a yet outstanding chapter of my dissertation, I compare the textual
          variation between multiple manuscripts of a single gospel to the
          variation that appears between multiple gospels in a single
          manuscript. A number of prominent scholars have argued that the
          earliest books about Jesus are so similar to one another that ancient
          readers would not have identified them as discrete authorial works but
          as multiple versions of a single work (Parker 1997, Broadhead 2017,
          Larsen 2019). A rigorous evaluation of this claim requires some new
          method for quantifying the similarity of multiple versions of a text.
        </p>
        <p class="paragraph">
          Edit distance, as defined by Vladimir Levenshtein, measures the number
          of editorial operations required to conform one string of characters
          to another. I believe that a modified form of the algorithm proposed
          by Levenshtein can be used to map the relationship between gospel
          manuscripts in a consistent and methodologically rigorous way. There
          is a problem, however, with the basic Damerau-Levenshtein distance
          algorithm. It counts additions, deletions, and adjacent transpositions
          as single operations. It does not, however, recognize substitution and
          adjacent block transposition. This kind of change, however, is a
          common feature of pre-modern textual transmission. I will use the
          research funding, therefore, to hire a software engineer to produce a
          calculator that incorporates modifications to the algorithm proposed
          by Dana Sahpira and James A. Storer (2007) and Tina Xia (2008) in
          order to recognize these operations.
        </p>
        <p class="paragraph">
          Furthermore, none of the publicly available calculators permit
          sufficiently long strings. The modified calculator will, therefore,
          permit 300-character strings. The edit distance calculator cannot, of
          course, be applied directly to manuscript transcriptions. If the
          calculator operated letter-by-letter, the omission of a long word
          would produce a higher edit distance than the omission of a short
          word. Transcriptions should, therefore, be converted into strings with
          a unique symbol corresponding to each word. This process is extremely
          time consuming. There are ninety-five stories present in all three
          synoptic gospels that must be compared in five different manuscripts.
          Done by hand, the conversion of a single story requires three to four
          hours. Furthermore, this procedure is error prone. It is plainly not
          feasible to conduct such an operation by hand. I will, therefore, use
          additional funding from the Julian Price fellowship to pay for the
          development of a simple program that assigns a symbol to unique words
          in the transcriptions. This will automate the conversion of text to
          text string thereby expediting the process and significantly improve
          its accuracy. Used in tandem, these two programs are an efficient,
          accurate, and transparent tool for quantifying the similarity of two
          texts.
        </p>
        <p class="paragraph">
          Unfortunately, this process cannot be automated entirely. Generalized
          (i.e. non- adjacent) block transposition is a recognizable source of
          variation in most premodern text traditions. Writing an algorithm that
          can recognize such a transformation as a single edit operation,
          however, is an NP-hard problem. It will be necessary, therefore, to
          pre- screen all ninety-five test passages in all three gospels in all
          five manuscripts for any such block transpositions and adjust the
          final edit distance accordingly. The Julian Price fellowship will give
          me the time to develop these twin programs, pre-screen the data, input
          the text strings, and incorporate the result into my dissertation. I
          will use this tool — composed of two fairly simple programs — to
          characterize the relative stability of the textual tradition of the
          synoptic gospels and evaluate popular claims about their identity as
          discrete works. This will clarify the role of authors and redactors as
          distinct from copyists in the creation of the gospels. The tool,
          however, has potential for application beyond my dissertation
          research. The first step in “traditional” textual criticism is
          grouping together related witnesses — usually on the basis of randomly
          selected test passages. Provided with transcriptions, the edit
          distance tool I am proposing to develop could be used to automate this
          step. This would be especially useful for certain text traditions,
          like the Byzantine families of the New Testament text, where thousands
          of nearly identical copies survive. I would, therefore, make the
          software funded by the Julian Price research fellowship publicly
          available. Furthermore, I would promote the tool and the usefulness of
          Levenshtein distance metrics in a separate publication, submitted to
          the open access journal Textual Criticism.
        </p>
      </div>
      <div class="links">
        <a
          href="https://github.com/NathOrmond/nt-redaction/projects/1"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Project Tasks
        </a>
        <a
          href="https://github.com/NathOrmond/nt-redaction"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style>
.container {
  margin: 150px auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
  padding-bottom: 25px;
  margin: 10px;
}

.paragraph {
  text-align: left;
  margin: 5px;
  margin-left: 40px;
  margin-right: 40px;
  padding: 10px;
}
</style>
