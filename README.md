# Azure-Policy-for-AGID-PNRR-Italy

l'AGID, [Agenzia per l'Italia Digitale](https://www.agid.gov.it/), ha emanato un REGOLAMENTO RECANTE I LIVELLI MINIMI DI SICUREZZA, CAPACITÀ ELABORATIVA, RISPARMIO ENERGETICO E AFFIDABILITÀ DELLE INFRASTRUTTURE DIGITALI PER LA PA E LE CARATTERISTICHE DI QUALITÀ, SICUREZZA, PERFORMANCE E SCALABILITÀ, PORTABILITÀ DEI SERVIZI CLOUD PER LA PUBBLICA AMMINISTRAZIONE, LE MODALITÀ DI MIGRAZIONE NONCHÉ LE MODALITÀ DI QUALIFICAZIONE DEI SERVIZI CLOUD PER LA PUBBLICA AMMINISTRAZIONE.

Questo regolamento è [scaricabile a questo link](https://trasparenza.agid.gov.it/moduli/downloadFile.php?file=oggetto_allegati/213481843250O__ORegolamento+servizi+cloud.pdf)

[Azure Policy](https://learn.microsoft.com/en-us/azure/governance/policy/overview) è un servizio di Microsoft Azure che ti consente di creare, gestire e applicare regole per l'uso delle risorse di Azure in modo coerente e coerente all'interno dell'organizzazione. È possibile utilizzare Azure Policy per definire le regole relative alla distribuzione e alla configurazione delle risorse di Azure, per esempio specificando i tipi di risorse che possono essere distribuite o le impostazioni di configurazione consentite per le risorse. Azure Policy viene spesso utilizzato per garantire il rispetto degli standard aziendali, delle linee guida per la sicurezza e delle normative di conformità.


Obiettivo di questo repository è mappare, ove possibile, i requisiti indicati dal regolamento AGID con delle policy applicabili in ambito workload su Azure.

> **Note**
> 
> ogni controllo richiesto sotto può essere associato a nessuna, una o più policy definition. Non tutti i requisiti sono gestibili da Azure Policy. Ove non posibile, una Azure Policy ad intervento manuale è inserita per usare l'infrastruttura Azure come task-list delle verifiche fatte/da fare sui sistemi.


| ID | Titolo | Requisito | ID_ACN | Policy Name | Effect | Version (GitHub)
|---|---|---|---|---|---|---|
| SR-PSN-001 | disponibilità infrastruttura | L’indice di disponibilità dell’infrastruttura digitale deve essere pari al - 99,98% al netto dei fermi programmati (ovvero pari a 17h, 31m, 53s in un anno solare) - 99,6 % comprendendo i fermi programmati (ovvero pari a 1 giorno 11h, 3m, 47s in un anno solare) | A.AA-1 |
| SR-PSN-002 | Monitoraggio disponibilità dell'infrastruttura | Il PSN mette in atto un monitoraggio attivo per garantire il rispetto degli indici di disponibilità così come definiti nel requisito REQ-GV-001 | AA.A-1 | Log Analytics extension should be enabled on VM | AuditIfNotExists | [2.0.1-preview](https://github.com/Azure/azure-policy/blob/master/built-in-policies/policyDefinitions/Monitoring/LogAnalytics_OSImage_Audit.json)
| SR-PSN-003 | Alta Affidabilità | I CED del PSN sono dotati di soluzioni hardware e software (apparati di rete e sicurezza, storage, servizi di virtualizzazione, etc.) per la configurazione dei servizi in alta affidabilità. Devono essere inoltre messe a disposizione capability e funzionalità a supporto di configurazioni dei servizi in alta affidabilità quali a. Scelta della replica locale dei dati per un servizio storage; b. Presenza di servizi di bilanciamento di carico; c. Meccanismi di anti-affinity per la distribuzione delle istanze computazionali. | A.AA-2 | lorem-ipsut-dixit | Manual | [lorem](lorem.json)
| ... |
| ... |

