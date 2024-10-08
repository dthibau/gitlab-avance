# Utiliser une image de base Ubuntu
FROM ubuntu:22.04

# Définir des variables d'environnement pour JMeter
ENV JMETER_VERSION=5.6
ENV JMETER_HOME=/opt/apache-jmeter-$JMETER_VERSION
ENV PATH=$JMETER_HOME/bin:$PATH

# Mettre à jour les paquets et installer les dépendances
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        openjdk-21-jdk \
        curl \
        wget \
        unzip && \
    # Télécharger et extraire JMeter
    wget https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-$JMETER_VERSION.zip && \
    unzip apache-jmeter-$JMETER_VERSION.zip -d /opt && \
    rm apache-jmeter-$JMETER_VERSION.zip && \
    # Nettoyer les caches APT
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Définir le répertoire de travail
WORKDIR /app

# Commande par défaut (peut être remplacée lors de l'exécution du conteneur)
CMD ["bash"]
