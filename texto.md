--- a/paper.md
+++ b/paper.md
@@
 ---
 title: "ATAS - Academic Text Analysis System"
 tags:
 - NLP
 - Content Analysis
 - Humanities
 - Text Analysis
 - Geography
 - Python
 authors:
   - name: "Alides Baptista Chimin Junior"
     orcid: "0000-0002-7436-390X"
     affiliation: "1"
 affiliations:
   - name: "Universidade Estadual do Centro-Oeste (UNICENTRO)"
     index: 1
 date: 18 February 2025
 bibliography: paper.bib
 ---
 
-# Abstract
+# Summary
 
-The ATAS - Academic Text Analysis System (Brazilian Portuguese SATA - Sistema de Análise de Textos Acadêmicos) is an open-source software developed to assist researchers in textual content analysis. Inspired by the methodology of @Bardin:2011, ATAS facilitates the extraction, filtering, and statistical analysis of academic texts, enabling the identification of semantic and linguistic patterns.
-The software is particularly useful for researchers in the Humanities and Social Sciences, providing tools for analyzing keywords, bigrams, lexical categories, and other quantitative metrics of textual analysis. It integrates natural language processing (NLP) and allows data export to software such as @Gephi:2009 for semantic network analysis.
-We emphasize that the tools are in Portuguese, as they were developed by a Brazilian researcher and are being used by the GEPES and GETE research groups.
+The **ATAS – Academic Text Analysis System** (Brazilian Portuguese **SATA – Sistema de Análise de Textos Acadêmicos**) is open-source software to support **textual content analysis**. Inspired by **Bardin’s method** [@Bardin:2020], ATAS streamlines **extraction, filtering, and statistical analysis** of academic texts to surface semantic and linguistic patterns. It is particularly useful to **Humanities and Social Sciences** researchers, offering tools for **keywords, bigrams, lexical categories**, and other quantitative text measures. ATAS integrates **NLP** workflows and exports data to tools such as **Gephi** for semantic network analysis [@Gephi].
+
+The toolset is localized for **Brazilian Portuguese** and is actively used by the **GETE – Grupo de Estudos Territoriais (Territorial Studies Group)** at **UEPG** and the **GEPES – Grupo de Pesquisa Redes de Poder, Migrações e Dinâmicas Territoriais (Research Group on Power Networks, Migrations, and Territorial Dynamics)** at **UNICENTRO** (Brazil), both operating in **Master’s and PhD** programs.
 
 # Statement of Need
 
-In the Brazilian Humanities and Social Sciences research context, many scholars still rely on manual or semi-manual methods to process and analyze large textual corpora. According to @Metzler:2016, barriers such as limited programming skills, lack of access to adequate infrastructure, and scarce training opportunities hinder the adoption of computational approaches in these fields. As a result, essential tasks like identifying thematic patterns, generating bigram networks, classifying authors by gender, and calculating lexical statistics often become labor-intensive and error-prone.
-The ATAS – Academic Text Analysis System addresses these issues by providing an open-source, graphical-interface-based solution that automates these processes without requiring advanced technical expertise. By integrating Natural Language Processing (NLP) capabilities in Brazilian Portuguese, ATAS bridges the gap between sophisticated analytical methods and their practical usability for non-technical researchers. This directly supports more equitable access to computational tools in contexts where language and resource limitations frequently exclude researchers from digital scholarship.
-Beyond facilitating traditional content analysis, ATAS expands methodological possibilities for examining the relationship between discourse and spatiality. While Geographic Information Systems (GIS) are powerful tools for spatial analysis and thematic cartography, their architecture — based on discrete vector and raster data structures — tends to produce static “snapshots” of space. This structural limitation often prevents them from representing the inherently dynamic, processual, and socially constructed nature of geographic phenomena.
-As highlighted by @Harvey:2005 and @Harvey:1980, and further developed by @Santos:1996 and @Santos:1978, geography extends far beyond cartographic representation. Space is not merely a neutral container of events, but a social, political, and economic construct permeated by power relations, symbolic appropriation, and subjective experiences — dimensions that resist reduction to numerical variables in a GIS database.
-ATAS offers a methodological alternative by enabling the extraction and analysis of “discursive spatialities” — the ways in which space is constructed, contested, and redefined through language — using spatial statistics and semantic networks directly from textual data. In doing so, it complements rather than replaces cartography, offering researchers in the Humanities and Social Sciences a way to capture spatial meaning that is processual, contextual, and deeply embedded in discourse.
+In Brazil’s Humanities and Social Sciences, many scholars still rely on manual or semi-manual workflows to process large textual corpora. Historical barriers—limited programming experience, scarce infrastructure, and uneven training—have hindered the adoption of computational methods [@metzler2016]. At the same time, **Large Language Models (LLMs)** have transformed NLP in recent years, opening powerful possibilities but also raising concerns about **language coverage, transparency, and reproducibility** [@Zhao:2023; @BigScience:2022; @Touvron:2023]. For **Portuguese (Brazil)** specifically, the ecosystem has improved with **encoder models** such as **BERTimbau** [@Souza:2020] and more recent PT-BR encoders [@Mello:2024], yet accessible, GUI-driven tools that operationalize these advances for **non-specialists** remain scarce.
+
+**ATAS** addresses this gap as an **open-source, GUI-based** system that automates key tasks—keyword filtering, bigram networks, lexical metrics—**without requiring advanced coding**. Localization to **Brazilian Portuguese** promotes equitable access to computational analysis and supports reproducible research pipelines for Human Geography and allied fields.
+
+Beyond facilitating content analysis, ATAS helps investigate how **discourse constitutes space**. In Human Geography, **space** is socially produced and relational rather than a neutral container [@Lefebvre:1991; @Massey:2005]. While GIS excels at mapping and spatial querying, its discrete data structures can under-represent **processual and discursive spatialities**. ATAS complements cartography by extracting **semantic networks and entities** directly from text, enabling researchers to track how places, actors, and relations are constructed, contested, and reconfigured in academic and policy discourse.
+
+## System overview
+![ATAS architecture and workflow.\label{fig:atas-arch}](docs/figures/atas_architecture.png){ width=70% }
 
 # Features and Usage
 
 ## 1. Text Filtering (Brazilian Portuguese: Filtragem de Texto)
 
 Extracts verbs, adjectives, and nouns from texts, facilitating qualitative analyses.
@@
 ## 4. Text Statistics (Brazilian Portuguese: Estatísticas de Texto)
 
-Provides quantitative metrics such as **word frequency, named entities, and lexical diversity**. These metrics assist researchers in identifying thematic emphases, recurring actors, and stylistic features in academic texts.
+Provides quantitative metrics such as **word frequency, named entities, and lexical diversity** to surface thematic emphases, recurring actors, and stylistic features in academic texts.
 
-- **Libraries used:** `spaCy`, `pandas`
+- **Libraries used:** `spaCy`, `pandas`
 - **How to use:**
   1. Go to the Text Statistics option.
   2. Select a text file.
   3. The system presents a detailed statistical report, including **word clouds and graphs**.
 
-*Note:* Sentiment analysis is under development and will be integrated in future releases using models specifically trained for Brazilian Portuguese (e.g., Stanza, NLPNet, Udpipe).
+*Note:* Sentiment analysis will be integrated in future releases with **Portuguese-specific models** (e.g., Stanza, NLPNet, UDPipe) and, where appropriate, **open LLMs** fine-tuned for PT-BR to support tasks such as summarization—while preserving ATAS’ principles of **openness, transparency, and independence from proprietary APIs** [@BigScience:2022; @Touvron:2023].
@@
 # Implementation
 
 ATAS is developed in **Python 3.8+** and utilizes:
 
 - **`spaCy`** for text processing.
 - **`pandas`** for data manipulation.
-- **`tkinter`** and **`ttkbootstrap`** for the graphical interface.
-- **`gender_guesser`** for gender identification.
+- **`tkinter`** and **`ttkbootstrap`** for the graphical interface.
+- **`gender_guesser`** for gender identification.
 
-While the current version relies primarily on `spaCy`, future developments will include support for alternative Natural Language Processing libraries (e.g., Stanza, NLPNet, Udpipe) to increase flexibility and expand coverage for Brazilian Portuguese. Sentiment analysis is also planned for future releases through the integration of models specifically trained for Portuguese.
-The source code is available on GitHub: [https://github.com/AlidesChimin/SATA](https://github.com/AlidesChimin/SATA)
+While the current version relies primarily on `spaCy`, future developments will add **Stanza/NLPNet/UDPipe** backends and optional **open LLM** components for PT-BR tasks, keeping the stack reproducible and OSI-compliant. The source code is available on GitHub: <https://github.com/AlidesChimin/SATA>.
@@
 # References
 
 Refer to the `paper.bib` file for the complete list of references.
@@
 # Acknowledgments
 
-I thank the project collaborators and the research groups GEPES and GETE, who influenced the conception of this software.
+I thank the project collaborators and the research groups **GETE (UEPG)** and **GEPES (UNICENTRO)**, whose ongoing use cases and feedback have shaped ATAS’ development.
@@
 🔗 **Zenodo DOI**: [10.5281/zenodo.14868064](https://doi.org/10.5281/zenodo.14868064)

