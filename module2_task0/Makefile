build:	## compile the source code of the application to a binary named awesome-api
	go get github.com/gorilla/mux
	go build

run:	## Run the application in background by executing the binary awesome-api
	./awesome-api >./awesome-api.log 2>&1 &

stop:	## Stop the application
	kill "$(shell pgrep awesome-api)"

clean:	## Delete the binary awesome-api and the log file awesome-api.log
	- make stop
	rm ./awesome-api ./awesome-api.log

test:	## Check expected behavior
	curl http://localhost:9999
	curl http://localhost:9999/health

help:	## Show this help.
	@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'
