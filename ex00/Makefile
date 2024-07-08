# VARIABLES

NAME	=	convert.exe

SRCS	=	main.cpp

OBJ_DIR	=	obj/

OBJS	=	$(addprefix $(OBJ_DIR), $(SRCS:.cpp=.o))

CC		=	c++
CFLAGS	=	-Wall -Wextra -Werror -std=c++98

GREEN	=	\033[0;32m
RED	=	\033[0;31m
YELLOW	=	\033[0;33m
CYAN	=	\033[0;36m
NC		=	\033[0m

# RULES

all: $(NAME)

$(NAME): $(OBJS)
	@echo "$(YELLOW)Compiling $(NAME)...$(NC)"
	@$(CC) $(CFLAGS) -o $(NAME) $(OBJS)
	@echo "$(GREEN)$(NAME) compiled successfully.$(NC)"

$(OBJ_DIR)%.o: %.cpp
	@if [ ! -d $(OBJ_DIR) ]; then mkdir $(OBJ_DIR); fi
	@echo "$(CYAN)Compiling $<...$(NC)"
	@$(CC) $(CFLAGS) -c $< -o $@

clean:
	@if [ -d $(OBJ_DIR) ]; then \
		echo "$(RED)Removing $(OBJ_DIR)...$(NC)"; \
		rm -rf $(OBJ_DIR); \
		echo "$(RED)$(OBJ_DIR) removed.$(NC)"; \
	fi

fclean: clean
	@if [ -f $(NAME) ]; then \
		echo "$(RED)Removing $(NAME)...$(NC)"; \
		rm -f $(NAME); \
		echo "$(RED)$(NAME) removed.$(NC)"; \
	fi

re: fclean all

.PHONY: all clean fclean re