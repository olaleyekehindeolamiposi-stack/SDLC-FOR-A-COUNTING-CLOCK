# SDLC-FOR-A-COUNTING-CLOCK
NAME: OLALEYE-KEHINDE OLAMIPOSI MATRIC NO : 24/15918 SOFTWARE ENGINEERING 
import time
import os
import sys

def clear_screen():
    # Windows
    if os.name == 'nt':
        os.system('cls')
    # macOS / Linux
    else:
        os.system('clear')

def main():
    seconds = 0
    minutes = 0
    hours = 0

    print("\n   Counting Clock")
    print("   ───────────────\n")
    print("   Press Ctrl+C to stop\n")

    try:
        while True:
            clear_screen()

            print("\n\n")
            print(f"        {hours:02d} : {minutes:02d} : {seconds:02d}")
            print("      ────────────────\n")

            seconds += 1

            if seconds == 60:
                seconds = 0
                minutes += 1
                if minutes == 60:
                    minutes = 0
                    hours += 1

            # Sleep for ~1 second (a bit less to account for overhead)
            time.sleep(0.98)

    except KeyboardInterrupt:
        print("\n\nStopped.\n")
        sys.exit(0)

if __name__ == "__main__":
    main()
