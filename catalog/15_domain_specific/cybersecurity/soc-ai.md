# IA pour les SOC (Security Operations Centers)

> Application de l'IA dans les centres de operations de securite - detection, triage et reponse automatisee

## Metadata
| Field | Value |
|-------|-------|
| **Category** | 15_domain_specific |
| **URL** | N/A (domaine transversal) |
| **Last Verified** | 2026-04-01 |
| **Status** | Active |
| **Maturity** | Production |

## What It Does
L'IA transforme les SOC en automatisant la detection des menaces, le triage des alertes, l'investigation et la reponse aux incidents. Les analystes SOC sont submerges d'alertes (souvent >10,000/jour) dont 90%+ sont des faux positifs. L'IA permet de filtrer, prioriser et repondre automatiquement.

## Key Applications

### 1. Triage automatique des alertes
- Classification des alertes par severite et type
- Deduplication et correlation d'evenements
- Reduction de 80-95% du bruit d'alertes

### 2. Detection d'anomalies
- Analyse comportementale (UEBA - User and Entity Behavior Analytics)
- Detection de mouvements lateraux
- Identification de menaces zero-day

### 3. Investigation assistee par IA
- Analyse automatique des logs et artefacts
- Enrichissement contextuel (threat intelligence)
- Generation de timelines d'incidents

### 4. Reponse automatisee (SOAR)
- Playbooks automatises de reponse
- Isolation automatique de systemes compromis
- Blocage d'IOCs en temps reel

## Outils et Plateformes

### Commercial
| Outil | Editeur | Description |
|-------|---------|-------------|
| Microsoft Sentinel + Copilot for Security | Microsoft | SIEM + IA generative |
| CrowdStrike Charlotte AI | CrowdStrike | Assistant IA pour SOC |
| Splunk AI Assistant | Cisco/Splunk | IA dans le SIEM |
| Google SecOps (Chronicle) + Gemini | Google | SIEM cloud + IA |
| Elastic Security AI | Elastic | Detection + IA |

### Open Source
| Outil | Description |
|-------|-------------|
| Wazuh | SIEM/XDR open source (integration IA possible) |
| TheHive + Cortex | Plateforme de reponse incidents |
| MISP | Plateforme de threat intelligence |
| Sigma Rules | Regles de detection universelles |

## Architecture Type SOC + IA
```
Sources de logs (firewall, EDR, cloud, apps)
    |
    v
SIEM (Sentinel/Splunk/Elastic)
    |
    v
IA Layer
    ├── Triage automatique (classification, dedup)
    ├── Detection anomalies (UEBA, ML)
    ├── Enrichissement (threat intel, IOC lookup)
    └── Correlation (graph analysis)
    |
    v
SOAR (playbooks automatises)
    |
    v
Analyste SOC (cas complexes uniquement)
```

## Enterprise Relevance
| Dimension | Rating (1-5) | Notes |
|-----------|-------------|-------|
| **Production Readiness** | 4 | Solutions commerciales matures, open source en rattrapage |
| **Security** | 5 | C'est le domaine meme de la securite |
| **Scalability** | 4 | Cloud-native, mais couteux a grande echelle |
| **Support/Community** | 4 | Ecosysteme mature (SIEM, SOAR, EDR) |
| **Documentation** | 4 | Docs vendors + communaute cybersec active |
| **Integration Ease** | 3 | Integration complexe multi-sources |

## Use Cases Enterprise
1. **Reduction fatigue analyste** : 90%+ alertes traitees automatiquement
2. **Detection avancee** : menaces invisibles aux regles statiques
3. **Reponse rapide** : temps de reponse reduit de heures a minutes
4. **Compliance** : rapports automatises pour NIS2, RGPD, ISO 27001

## Strengths
- Impact business mesurable (reduction MTTD/MTTR)
- Marche mature avec solutions eprouvees
- Combine bien avec les agents IA (voir cat. 02)

## Limitations
- Risque de faux negatifs si mal calibre
- Necessite des donnees de qualite (garbage in, garbage out)
- Cout eleve des solutions commerciales
- Complexite d'integration multi-vendeurs

## References
- [MITRE ATT&CK](https://attack.mitre.org) - Framework de reference
- [Sigma Rules](https://github.com/SigmaHQ/sigma) - Regles de detection open source
- [Wazuh](https://wazuh.com) - SIEM open source
- Voir aussi : catalog/12_enterprise_integration/compliance/nis2-ai-implications.md

## Notes
- L'IA pour SOC est un domaine clé pour l'intégration enterprise
- Les agents IA (cat. 02) peuvent servir d'analystes SOC autonomes
- MCP (cat. 03) peut connecter des LLMs aux outils SOC (SIEM, SOAR)
