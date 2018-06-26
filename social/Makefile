PROJ=proposal

TARGET=$(PROJ).pdf
SOURCE=$(PROJ).tex

$(TARGET): $(SOURCE)
	pdflatex $(SOURCE)
	pdflatex $(SOURCE)
	pdflatex $(SOURCE)

clean:
	rm -rf $(TARGET) $(PROJ).{log,aux}