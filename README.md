========================

# CyberAgressionAdo-v1
Dataset containing annotated scenarios in French mimicking cyber aggression situations tat may occur on private instant messaging platforms among teens.

v 2.0: April 6 2023

https://github.com/aollagnier/CyberAgressionAdo-v2.2

========================

## 1) DESCRIPTION
 
The CyberAgressionAdo-v1 dataset contains 19 aggressive multiparty chats in French collected through a role-playing game in high-schools. This dataset relies on scenarios mimicking cyber aggression situations that may occur among teens, involving topics such as the ethnic origin, the religion or the color of skin. The collected conversations have been annotated considering several layers, as the participant roles, the presence of hate speech, the type of verbal abuse present in the message, and whether utterances use different humor figurative devices such as sarcasm or irony.

## 2) FORMAT

Annotated conversations are located in the folder `scenarii`. Each file correspond to one of the scenario described in `scenarii_description.pdf. Each scenario is included in CSV format as follows:

```
ID  TIME    NAME    TEXT    ROLE    TARGET    HATE SPEECH    VERBAL ABUSE    HUMOR
```

Whenever a label is not given, a value NONE is inserted (e.g. INSTANCE  NOT NULL    NULL)

The labels used in the annotation are listed below.

## 3) LABELS

### ROLE / TARGET

- (victim) person who is harassed
- (bully) erson who initiates the harassment
- (bystander-defender) person who helps the victim and discourages the harasser
- (bystander-assistant) person who takes part in the actions of the harasser
- (conciliator) a common friend of the bully and the victim mediating the disagreement among active participants

In our annotation, we label a post according to the role attributed to the participant in the corresponding scenario. The target is tagged only for messages containing "VERBAL ABUSE". The targets can be multiple and refer to the role of the participant(s) considering the context of the ongoing discourse at large. In other words, not only the previous message is considered due to the untangled nature of multi-party chats. The target(s) is/are identified according to the message it answers. 

### HATE SPEECH

Here, we rely on the definition of hate speech as "content that mocks, insults or discriminates against a person or group based on specific characteristics such as color, ethnicity, gender, sexual orientation, nationality, religion, or other characteristics".

- (no) given to all those human speech samples which do not exhibit aggression in any form.
- (yes) messages containng any form of non-acceptable language (profanity) or a targeted offense, which can be veiled or direct.

### VERBAL ABUSE

- (blaming) making the victim believe they are responsible for the abusive behavior or that they bring the verbal abuse upon themselves 
- (name-calling) abusive, derogatory language or insults that chip away at the target’s self-esteem, sense of self-worth, and self-concept.
- (threat) statements meant to frighten, control, and manipulate the victim into compliance.
- (denigration) harsh remarks that are meant to make the person feel bad about themselves and are not constructive, but deliberate and hurtful.
- (aggression-other) content corresponding to other types of abusive, derogatory language or insults deliberately harmful not fitting in the other categories.

According to the definition of HATE SPEECH adopted, a message can contain verbal abuse but NOT be considered as hate speech.

### HUMOR

The annotation relies on a binary categorisation, namely, humor and non-humorous.

- (no) given to all those human speech samples which do not exhibit humorous markers.
- (yes) content including laughing emojis or interjections such as "ptdr" (EN: laughing my ass off) or "lol". Content initiating in return such humorous markers are also identified as humorous.

## 4) CITING THE DATASET

If you use this dataset we kindly ask you to include a reference to the paper below.

```
@inproceedings{DBLP:conf/lrec/OllagnierCVB22,
  author    = {Ana{\"{i}}s Ollagnier and
               Elena Cabrio and
               Serena Villata and
               Catherine Blaya},
  editor    = {Nicoletta Calzolari and
               Fr{\'{e}}d{\'{e}}ric B{\'{e}}chet and
               Philippe Blache and
               Khalid Choukri and
               Christopher Cieri and
               Thierry Declerck and
               Sara Goggi and
               Hitoshi Isahara and
               Bente Maegaard and
               Joseph Mariani and
               H{\'{e}}l{\`{e}}ne Mazo and
               Jan Odijk and
               Stelios Piperidis},
  title     = {CyberAgressionAdo-v1: a Dataset of Annotated Online Aggressions in
               French Collected through a Role-playing Game},
  booktitle = {Proceedings of the Thirteenth Language Resources and Evaluation Conference,
               {LREC} 2022, Marseille, France, 20-25 June 2022},
  pages     = {867--875},
  publisher = {European Language Resources Association},
  year      = {2022},
  url       = {https://aclanthology.org/2022.lrec-1.91},
  timestamp = {Mon, 10 Oct 2022 16:57:52 +0200},
  biburl    = {https://dblp.org/rec/conf/lrec/OllagnierCVB22.bib},
  bibsource = {dblp computer science bibliography, https://dblp.org}
}
```
