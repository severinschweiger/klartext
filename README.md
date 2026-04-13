# klartext

Ein Claude Skill, der typische KI-Schreibmuster aus deutschen Texten entfernt. Speziell für deutsche AI-Tells gebaut, kein 1:1-Port eines englischen Humanizers.

Gemacht für: Blog-Posts, Newsletter, Landing-Pages, Social-Media-Content, Produktbeschreibungen. Alles, was nach Mensch klingen soll und nicht nach ChatGPT.

## Was der Skill macht

Er scannt Text auf 36 KI-typische Muster und schreibt sie natürlicher um. Davon sind 7 Muster markiert als **deutschspezifisch (★)**, weil sie nur im Deutschen als KI-Tell funktionieren:

- **„Jedoch" statt „aber"** (ein Text ohne ein einziges „aber" ist fast immer maschinell)
- **Genitivketten** („im Rahmen der Umsetzung der Strategie der Abteilung")
- **Nominalstil und Verbvermeidung** („Die Durchführung der Optimierung" statt „Wir optimieren")
- **Archaische Demonstrative und Amtsdeutsch** („hierbei", „diesbezüglich", „hinsichtlich")
- **Sowohl-als-auch-Übernutzung**
- **Aufzählende Absatzanfänge** („Darüber hinaus... Ferner... Zudem...")
- **Übertriebene Formalität ohne Umgangssprache** (kein einziges „halt", „mal", „einfach")

Dazu die klassischen KI-Tells: Bedeutungs-Inflation, Werbesprache, Dreiergruppen, Synonym-Karussell, Gedankenstrich-Übernutzung, Emojis, Chatbot-Floskeln, Schmeichlerei, Füllphrasen, übertriebenes Hedging und generische Positiv-Schlüsse.

Am Anfang des Skills: **Quick-Check mit den 10 lautesten Signalen.** Wenn drei oder mehr zutreffen, ist der Text fast sicher KI-generiert.

## Installation

### Claude.ai (einfachster Weg)

1. Oben rechts auf den grünen **Code**-Button klicken, dann **Download ZIP**
2. In [claude.ai](https://claude.ai) links in der Sidebar auf **Anpassen**
3. Dort auf **Skills**
4. Oben rechts auf das **+** klicken, dann **Skill hochladen**
5. Die heruntergeladene ZIP auswählen
6. Fertig. Der Skill taucht unter „Persönliche Skills" als `klartext` auf

Danach einfach Claude sagen: „Nutze klartext auf folgenden Text: ..."

### Claude Code

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/severinschweiger/klartext.git ~/.claude/skills/klartext
```

Dann im Chat aufrufen mit `/klartext`.

### Manuelle Nutzung (ohne Skill-System)

`SKILL.md` öffnen, Inhalt kopieren, als System-Prompt oder am Anfang des Chats einfügen.

## Nutzung

**Minimal:**
```
Bring diesen Text in Klartext:
[dein Text]
```

**Mit Stimm-Kalibrierung (besser):**
```
Bring diesen Text in Klartext. Als Referenz für meine Stimme, hier eine Schreibprobe von mir:
[deine Schreibprobe]

Text:
[zu überarbeitender Text]
```

Der Skill liefert:
1. Eine erste Überarbeitung
2. Ein Selbst-Audit, was am Draft noch nach KI klingt
3. Die finale Version nach dem Audit
4. Optional: Zusammenfassung der Änderungen

## Warum nicht einfach ein englisches Humanizer-Tool?

Viele KI-Schreibmuster sind sprachspezifisch. „Stands as a testament" wird im Deutschen zu „ist ein Beleg für". Gleicher Tell, andere Wörter. Andere Tells sind deutsch-exklusiv: Nominalstil, Genitivketten, „jedoch" statt „aber", Amtsdeutsch, aufzählende Absatzanfänge.

Der stärkste davon ist die Abwesenheit von „aber". Menschliche Deutschschreiber benutzen „aber" ständig. KI-Deutsch weicht auf „jedoch", „allerdings", „nichtsdestotrotz" aus. Ein Text, in dem kein einziges „aber" vorkommt, ist fast immer maschinell. Das kriegt man mit einem englischen Humanizer nicht raus.

## Mitmachen

Issues und PRs willkommen. Besonders für neue deutsche KI-Tells, die mir noch nicht aufgefallen sind.

## Lizenz

MIT, siehe [LICENSE](LICENSE).

## Autor

[Severin Schweiger](https://severin-schweiger.com). Baut Claude-basierte Automationen für DACH-Shopify-Brands und dokumentiert das auf [TikTok](https://tiktok.com/@schweigerseverin) und [Instagram](https://instagram.com/schweigerseverin).
