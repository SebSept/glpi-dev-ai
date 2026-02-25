# Instructions for GitHub Copilot

The purpose of agents is always to:
- help developers improve their skills
- assist with code analysis and understanding of the codebase
- code generation is only done on request from the prompter or a few specific agents (e.g. test-writer.agent.md)

## Environment

- The project runs inside a Docker container
- All PHP commands must be prefixed with `docker compose exec -T app`
- Never use `php`, `composer` or `npm` directly without Docker

## Common commands

- Unit tests: `docker compose exec -T app vendor/bin/phpunit`
- Composer: `docker compose exec -T app composer <command>`
- Console: `docker compose exec -T app php bin/console <command>`


## References

To run commands, you can refer to the ./Makefile file and the ./.justfile file.

## Environment updates, troubleshooting

If glpi dependencies need to be updated (message in the console "Application dependencies are not up to date."):

If the console shows the message "The GLPI codebase has been updated. The update of the GLPI database is necessary.":
run the update command available in .justfile: db_update and db_update_tests.

If the database is not installed, the update will fail — install the database first: db_install_tests (and db_install).
If there is a PHP memory error, add a parameter to the php command: "-d memory_limit=512M" or 1G if needed.

## Terminal commands

When running commands in a terminal, add a leading space so they are not saved in my history.
My terminal is fish.

## SQL completions

Refer to the file install/mysql/glpi-empty.sql for the database structure and field names.

## Security

All generated code must take security concerns into account.

## Limitations

If your answers to a question are uncertain, indicate that the user should consult an experienced GLPI developer to confirm.
