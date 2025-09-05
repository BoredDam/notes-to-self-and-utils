# Virtual Environments

Un ambiente virtuale (venv) è un ambiente isolato e indipendente in cui è possibile installare pacchetti Python specifici per un progetto senza influenzare il sistema globale o altri progetti. Permettono quindi di gestire progetti separati con le proprie dipendenze, isolandone i pacchetti, comprese versioni specifiche, senza conflitti.

## First setup

Installa i pacchetti python3 e python3-virtualenv

```sh
sudo dnf install python3 python3-virtualenv
```

That's it!

## Creare un venv

Nella directory d'interesse, in cui verranno inseriti i propri script python, scrivere:

```sh
python3 -m venv nome_venv
```

Questo creerà un'omonima cartella all'interno della directory di lavoro, contenente tutti i file utili per l'ambiente virtuale

## Usare il venv e installare i pacchetti

All'interno della directory del progetto, esegui

```sh
source nome_venv/bin/activate
```

per attivare l'ambiente virtuale.

Da qui in poi, il terminale apparirà così:

```sh
(nome_venv) username@hostname:~/path/project$
```

Per installare qualsiasi pacchetto, usa pip install (solo se sei nel tuo venv, altrimenti lo installerai globalmente!).

```sh
(nome_venv) username@hostname:~/path/project$ pip install nome_pacchetto
```

Un esempio è il seguente:

```sh
(qiskit_venv) username@hostname:~/path/project$ pip install qiskit qiskit-ibm-runtime qiskit[visualization] jupyter
```

### Mostrare tutti i pacchetti installati

```sh
(nome_venv) username@hostname:~/path/project$ pip list
```

### Disinstallare un pacchetto

```sh
(nome_venv) username@hostname:~/path/project$ pip uninstall nome_pacchetto
```

## Uscire dal venv

Per uscire dal virtual environment e tornare al contesto globale, basterà scrivere:

```sh
deactivate
```

