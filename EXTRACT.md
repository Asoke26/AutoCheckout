1. Run `extract-data.sh`. The cpsdriver container will pause in a dummy task.
2. Press Ctrl-Z to stop the docker task, then type `bg`
3. Attach to the cpsdriver container with `docker exec -it autocheckout_cpsdriver_1 /bin/bash`
4. Make a csv directory where the files will be stored: `mkdir csv`
5. Run the script. This can take a while. `python3 cpsdriver/main.py`
6. Leave the container by pressing Ctrl-D or typing `exit`
7. Copy the csv files to your computer: `docker cp autocheckout_cpsdriver_1:/app/csv .`
8. End the container by typing `fg` then Ctrl-C twice

If you didn't run docker as sudo (as in extract\_data.sh), you may need to `rm -r data/mongo` between runs
