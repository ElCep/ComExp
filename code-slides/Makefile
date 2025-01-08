.PHONY: all clean

# Commandes pour compiler LaTeX et Biber
CC = pdflatex
BIBER = biber
EXAMPLES_DIR = .

# Le fichier principal à compiler
TARGET = hdr_delay

# Liste des fichiers inclus (tous les fichiers .tex dans les sous-dossiers)
INCLUDES = $(wildcard $(EXAMPLES_DIR)/*.tex $(EXAMPLES_DIR)/*/*.tex $(EXAMPLES_DIR)/*/*/*.tex)

# Fichiers source et cible
SRC = $(EXAMPLES_DIR)/$(TARGET).tex
PDF = $(EXAMPLES_DIR)/$(TARGET).pdf

# Règle principale pour générer le fichier PDF
all: $(PDF)

# Compilation du fichier PDF, incluant les fichiers annexes
$(PDF): $(SRC) $(INCLUDES)
	$(CC) -output-directory=$(EXAMPLES_DIR) $(SRC)
	$(BIBER) $(TARGET)
	$(CC) -output-directory=$(EXAMPLES_DIR) $(SRC)

# Nettoyage des fichiers temporaires générés par LaTeX et Biber
clean:
	rm -f $(EXAMPLES_DIR)/*.aux $(EXAMPLES_DIR)/*.bbl $(EXAMPLES_DIR)/*.bcf \
	      $(EXAMPLES_DIR)/*.blg $(EXAMPLES_DIR)/*.log $(EXAMPLES_DIR)/*.out \
	      $(EXAMPLES_DIR)/*.run.xml $(EXAMPLES_DIR)/*.toc $(EXAMPLES_DIR)/*.lof \
	      $(EXAMPLES_DIR)/*.lot $(EXAMPLES_DIR)/*.pdf
	rm -f $(EXAMPLES_DIR)/*/*.aux $(EXAMPLES_DIR)/*/*.log $(EXAMPLES_DIR)/*/*.out \
	      $(EXAMPLES_DIR)/*/*.bbl $(EXAMPLES_DIR)/*/*.bcf $(EXAMPLES_DIR)/*/*.blg \
	      $(EXAMPLES_DIR)/*/*.run.xml
