cmake_minimum_required(VERSION 3.27)
project(42sh C)

set(CMAKE_C_STANDARD 11)

include_directories(lib/my/include)


add_library(my STATIC
    lib/my/iomanip/my_getnbr.c
	lib/my/iomanip/my_put_nbr.c
	lib/my/iomanip/my_putchar.c
	lib/my/iomanip/my_putstr.c
	lib/my/iomanip/my_show_word_array.c
	lib/my/linked_list/append_node.c
	lib/my/my_printf/src/casts/floats.c
	lib/my/my_printf/src/casts/get_raw_str.c
	lib/my/my_printf/src/casts/signed_casts.c
	lib/my/my_printf/src/casts/string_casts.c
	lib/my/my_printf/src/casts/unsigned_casts.c
	lib/my/my_printf/src/casts/var_to_str.c
	lib/my/my_printf/src/formats/format.c
	lib/my/my_printf/src/formats/format_flags.c
	lib/my/my_printf/src/formats/format_precision.c
	lib/my/my_printf/src/formats/format_width.c
	lib/my/my_printf/src/get_formats/get_flags.c
	lib/my/my_printf/src/get_formats/get_format.c
	lib/my/my_printf/src/get_formats/get_params.c
	lib/my/my_printf/src/print/my_printf.c
	lib/my/my_printf/src/print/show_non_print.c
	lib/my/others/my_sort_int_array.c
	lib/my/others/my_sort_word_array.c
	lib/my/others/my_swap.c
	lib/my/others/my_free.c
	lib/my/strmanip/append_char.c
	lib/my/strmanip/contain.c
	lib/my/strmanip/my_memset.c
	lib/my/strmanip/my_revstr.c
	lib/my/strmanip/my_str_to_word_array.c
	lib/my/strmanip/my_strcat.c
	lib/my/strmanip/my_strcmp.c
	lib/my/strmanip/my_strcpy.c
	lib/my/strmanip/my_strdup.c
	lib/my/strmanip/my_strlen.c
	lib/my/strmanip/my_strncat.c
	lib/my/strmanip/my_strncmp.c
	lib/my/strmanip/my_strncpy.c
	lib/my/strmanip/my_strstr.c
	lib/my/strmanip/replace_str.c
	lib/my/strmanip/str_array_contain.c
	lib/my/strmanip/str_is_num.c
	lib/my/strmanip/strconcat.c
	lib/my/my_malloc/my_exit.c
	lib/my/my_malloc/my_malloc.c
)

include_directories(include)

add_executable(42sh
        src/backticks/backticks.c
        src/builtins/alias.c
        src/builtins/cd.c
        src/builtins/cd_get_infos.c
        src/builtins/echo.c
        src/builtins/env.c
        src/builtins/exit.c
        src/builtins/history.c
        src/builtins/set.c
        src/builtins/set2.c
        src/builtins/set3.c
        src/builtins/setenv.c
        src/builtins/unalias.c
        src/builtins/unset.c
        src/builtins/unsetenv.c
        src/exec_command/exec.c
        src/exec_command/find_command.c
        src/exec_command/pipe.c
        src/exec_command/redirects.c
        src/get_input/arrows.c
        src/get_input/remove_string_from_array.c
        src/get_input/shell_input.c
        src/get_input/special.c
        src/get_input/tab_globing.c
        src/get_input/tab_globing_print.c
        src/get_input/termios.c
        src/globals/env.c
        src/globals/free_stdin.c
        src/globals/is_exit.c
        src/globals/last_exit.c
        src/globals/out_fd.c
        src/globals/reset_buffer.c
        src/globals/std_in.c
        src/globing/globing.c
        src/history/history_manip.c
        src/history/init_history.c
        src/parse_input/aliases_in_parse.c
        src/parse_input/call_all_check.c
        src/parse_input/check_exec_manip.c
        src/parse_input/clear_input_str.c
        src/parse_input/delete_backslash.c
        src/parse_input/edit_input.c
        src/parse_input/generate_command.c
        src/parse_input/globing.c
        src/parse_input/heredoc.c
        src/parse_input/history_input.c
        src/parse_input/replace_variable.c
        src/parse_input/split_semicolon.c
        src/parse_input/str_to_word_array_input.c
        src/command.c
        src/exec_file.c
        src/init_vars.c
        src/main.c
        src/print_input.c)

target_link_libraries(42sh my)