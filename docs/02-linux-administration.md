# Linux Administration

## User and Group Management

A dedicated lab user named `labuser` was created for practical testing.

A group named `linuxlab` was created, and `labuser` was added
to that group.

## File Permissions

The directory `/opt/linux-lab` was created with:

- Owner: root
- Group: linuxlab
- Mode: 2770

The setgid permission allows new files and directories created
within this directory to inherit its group under normal conditions.

## Validation

The following checks were performed:

- Verified the lab user and group.
- Created a test file as `labuser`.
- Wrote test content to the file.
- Read the file as `labuser`.

## Result

Record the actual command outputs and test results here.
