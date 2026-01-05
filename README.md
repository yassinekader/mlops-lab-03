# DVC Setup Guide

## Étape 1 : Initialisation de DVC dans le projet

![dvc_init](images/dvc_init.png)

![list_folders_n_files_after_project_init](images/list_folders_n_files_after_project_init.png)

Initialisation de DVC pour permettre le suivi des fichiers volumineux et création des fichiers de configuration .dvc.

---

## Étape 2 : Versionner les données brutes avec DVC

![dvc_add_data_raw_csv](images/dvc_add_data_raw_csv.png)

![add_dvc_files_to_staging_area](images/add_dvc_files_to_staging_area.png)

![commit_message_suivi_du_dataset_with_dvc](images/commit_message_suivi_du_dataset_with_dvc.png)

![list_data_folder_after_using_dvc](images/list_data_folder_after_using_dvc.png)

Ajout du dataset `data/raw.csv` au suivi DVC. Le fichier original est remplacé par un pointeur `.dvc` qui est ensuite versionné avec Git.

---

## Étape 3 : Configuration d’un remote DVC

![simulate_dvc_remote_storage_using_local_folder](images/simulate_dvc_remote_storage_using_local_folder.png)

Création et configuration d'un dossier de stockage local (`dvc_storage`) agissant comme remote pour DVC.

---

## Étape 4 : Push des données dans le remote DVC

![dvc_push](images/dvc_push.png)

Envoi des fichiers suivis par DVC vers le remote de stockage configuré pour le partage.

---

## Étape 5 : Simulation d’une collaboration : supprimer localement et récupérer depuis DVC

![rm_data_csv_and_pull_it_using_dvc](images/rm_data_csv_and_pull_it_using_dvc.png)

![show_n_rows_from_the_data_on_local_repo_using_hash_from_dvc_file](images/show_n_rows_from_the_data_on_local_repo_using_hash_from_dvc_file.png)

Suppression du fichier local pour simuler une perte ou un nouvel environnement, puis récupération des données depuis le remote via `dvc pull`.

---

## Étape 6 : Création d’un pipeline reproductible dvc.yaml

![pipeline_prepare_train_evaluate_dvc](images/pipeline_prepare_train_evaluate_dvc.png)

![add_dvc_of_processed_and_train_stats_to_be_tracked_with_git](images/add_dvc_of_processed_and_train_stats_to_be_tracked_with_git.png)

Définition des étapes du pipeline (préparation, entraînement, évaluation) avec leurs dépendances et sorties dans le fichier `dvc.yaml`.

---

## Étape 7 : Reproduire automatiquement tout le pipeline

![dvc_repro](images/dvc_repro.png)

Utilisation de `dvc repro` pour réexécuter automatiquement uniquement les étapes du pipeline affectées par des modifications.
