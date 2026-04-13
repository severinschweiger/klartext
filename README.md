# klartext

Ein Claude Skill, der typische KI-Schreibmuster aus deutschen Texten entfernt. Kein 1:1-Port eines englischen Humanizers, sondern speziell für deutsche AI-Tells gebaut.

Gemacht für: Blog-Posts, Newsletter, Landing-Pages, Social-Media-Content, Produktbeschreibungen. Alles, was nach Mensch klingen soll und nicht nach ChatGPT.

## Was der Skill macht

Er scannt Text auf 28 KI-typische Muster und schreibt sie natürlicher um. Die wichtigsten:

- **Em-Dash und En-Dash als Satzzeichen** (harte Regel: null Toleranz)
- Bedeutungs-Inflation („markiert einen Wendepunkt", „spielt eine entscheidende Rolle")
- Werbesprache („hochwertig", „ganzheitlich", „vielfältig", „zahlreich")
- Nominalstil und Substantivierungsketten (ein deutsches Spezial-Problem)
- KI-Vokabular-Cluster („darüber hinaus", „somit", „im Kern")
- Negative Parallelismen („nicht nur X, sondern auch Y")
- Dreier-Listen, wo keine sein müssten
- Sycophantischer Ton
- Füllphrasen und Hedging
- „Im Kern / eigentlich geht es darum"-Pseudo-Tiefe
- Signposting („Schauen wir uns an...")
- Fragmentierte Überschriften
- Platzhalter-Wörter („zahlreich", „vielfältig", „diverse")

Dazu eine eigene Sektion zu Persönlichkeit und Stimme, weil sauber-aber-seelenlos genauso auffällig ist wie KI-Slop.

## Installation

### Claude.ai (einfachster Weg)

1. Oben rechts auf den grünen **Code**-Button klicken, dann **Download ZIP**
2. In [claude.ai](https://claude.ai) links in der Sidebar auf **Customize** klicken
3. Dort auf **Skills**
4. Oben rechts auf das **+** klicken, dann **Upload a skill**
5. Die heruntergeladene ZIP-Datei auswählen
6. Fertig. Der Skill taucht unter „My skills" auf

Danach kannst du Claude einfach sagen: „Nutze klartext auf folgenden Text: ..."

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

Viele KI-Schreibmuster sind sprachspezifisch. „Stands as a testament" wird im Deutschen zu „ist ein Beleg für". Gleicher Tell, andere Wörter. Andere Tells sind deutsch-exklusiv: der Nominalstil zum Beispiel („die Durchführung einer Überprüfung der..."), oder die Cluster aus „darüber hinaus / zudem / des Weiteren / somit".

Der wichtigste Grund ist aber der Em-Dash. Im Englischen ist er stilistisch diskutabel. Im Deutschen ist er der mit Abstand stärkste Verräter für KI-Output. Deutsche Muttersprachler schreiben so nicht. Dieser Skill behandelt ihn als absolutes No-Go, nicht als Stilfrage.

## Mitmachen

Issues und PRs willkommen. Besonders für neue deutsche KI-Tells, die mir noch nicht aufgefallen sind.

## Lizenz

MIT, siehe [LICENSE](LICENSE).

## Autor

[Severin Schweiger](https://severin-schweiger.com). Baut Claude-basierte Automationen für DACH-Shopify-Brands und dokumentiert das auf [TikTok](https://tiktok.com/@schweigerseverin) und [Instagram](https://instagram.com/schweigerseverin).
