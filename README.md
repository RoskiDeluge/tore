# Tore (TOtall REcall)

> [!WARNING]
> The project is designed for my personal needs only, and may not be suitable for everybody. I do not offer any support for it either. It's completely Open Source, fork it and adapt it to your needs.

## Quick Start

```console
$ cc -o nob nob.c
$ ./nob
$ sudo cp ./build/tore /usr/local/bin/
$ echo "tore" >> ~/.bashrc
```
---

# Tore - Task and Reminder Management CLI

Tore is a command-line tool for managing notifications and reminders. It stores data locally in a SQLite database at `~/.tore`.

## Commands

```bash
tore checkout
```
Shows all active notifications and fires off any due reminders.

```bash
tore notify <title>
```
Creates a new notification with the specified title.

```bash
tore dismiss <index>
```
Dismisses the notification at the given index. The index is shown when viewing notifications with `tore checkout`.

```bash
tore remind
```
View active reminders.

```bash
tore remind <title> <date> [period]
```
`date`: Must be in YYYY-MM-DD format \
`period` (optional): Specify recurring reminders using format like:
- `7d` - every 7 days
- `2w` - every 2 weeks
- `3m` - every 3 months
- `1y` - every year

```bash
tore forget <number>
```
Removes the reminder at the specified index number.

# Web Interface
```bash
tore serve
```
Starts a local web server at http://127.0.0.1:6969 that displays your active notifications and reminders in a browser interface.

```bash
tore version

```
Shows the Git hash of the current build.

# Features
- Local storage in SQLite database
- One-time and recurring reminders
- Browser-based dashboard
- Notification grouping
- Date-based scheduling

## Notifications vs Reminders

Notifications and Reminders are the two cornerstones of the Tore
paradigm and the difference between them is very important.

Notifications are your "Mailbox". You receive them so you can recall
the Thing. Notifications stay in your Mailbox until you explicitly
dismiss them.

Reminders are the generators of the Notifications. You schedule
Reminders to "fire off" Notifications into your Mailbox. Reminders can
also be configured to fire off Notifications periodically (every N
days, every N months, every N years, etc).

Just running `tore` in the terminal fires off all the necessary
Notifications and shows your Mailbox. This is why you put it into your
`.bashrc`, so you can always recall the Thing every time you open your
Terminal (and you open your Terminal every single day multiple times,
because you are a huge nerd).

For more information on how to manipulate Notifications and Reminders
run `tore help`.
