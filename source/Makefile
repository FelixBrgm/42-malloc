AR := ar rcs
# CFLAGS := -Wall -Werror -Wextra


ifeq ($(HOSTTYPE),)
HOSTTYPE := $(shell uname -m)_$(shell uname -s)
endif

NAME = libft_malloc_$(HOSTTYPE).so

# LINKED_LIST
MALLOC_C_FILES := malloc.c malloc_helper.c

# LIBS
CFILES := $(MALLOC_C_FILES)
OFILES := $(CFILES:.c=.o)

all: $(NAME)

$(NAME): $(OFILES)
	@$(AR) $(NAME) $(OFILES)
	@echo "Compiled!"

%.o : %.c
	@$(CC) -g -c $(CFLAGS) $< -o $@

clean: 
	@rm -f $(OFILES)
	@echo "Cleaned!"

fclean: clean
	@rm -f $(NAME)
	@rm -f ./tester
	@echo "FCleaned!"

re: fclean all

main: $(NAME)
	$(CC) -g $(CFLAGS) main.c -o tester $(NAME)