# Analyser av artikler fra ACL Anthology
[English README here](README_eng.md)
På ACL anthology er det over hundre tusen artikler relatert til språkteknologi. I dette repoet har vi kode for å:

1. [Bruke `aclanthology`-pakken](acl_sa-stats.ipynb) til å lese gjennom tittel og abstract for alle artiklene og hente ut de som er av interesse.
1. [Bruke Mistral OCR](acl_ocr.ipynb) for å konvertere artiklene til markdown.
1. [Bruke `google/gemini-2.5-flash`](acl_analysis-api.ipynb) for å lese innholdet og kategoriesere tekstene i henhold til promptet.
1. [Sammenstille og presentere funnene](acl_analysis-plot.ipynb)

I vårt tilfelle ønsker vi å analysere trender innen modellering for sentimentanalyse. I steg 1) setter vi årene vi er interessert i, og teksten "sentiment" som skal finnes i abstract til artiklene vi vil se nærmere på. I steg 2) setter vi sammen sidene vi får tilbake, og klipper av ved `# References`. I steg 3) instruerer vi klassifiseringen med promptet vi har valgt. I steg 4) sammenstiller vi resultatet og gjør en ekstra undersøkelse på de mest interessant tilfellene.

![](modeling_trends.jpg)

Husk at hvis vi ikke kvalitetssikrer resultatene, er de kun _estimater_ av hva som artiklene inneholder.

Markdown og klassifiseringsresultater for de 37 artiklene som ble klassifisert til å inneholde modellering som bruker fine-tuning av dekoder-modeller [er tilgjengelig her](FinetuningDecoder_papers.jsonl).
