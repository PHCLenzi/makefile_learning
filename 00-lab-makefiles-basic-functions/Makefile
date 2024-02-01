## test of some functions based on source code of linux-5.10 kernel from nvidia repo: https://nv-tegra.nvidia.com/r/gitweb?p=linux-5.10.git;a=commit;h=8009bb70a484d47d6d0b7bfe336e9e6836897f07
## Also, following this tutorial: https://makefiletutorial.com/#getting-started

KERNEL_OVERLAYS := ./test_1 ./test_2
override KERNEL_OVERLAYS := $(abspath $(KERNEL_OVERLAYS))
# hello:
# 	# @echo "Hello there" \
# 	# echo "CURDIR = $(CURDIR)" \
# 	# echo "KERNEL_OVERLAYS = $(KERNEL_OVERLAYS)"

define set_srctree_overlay
	overlay_name := $(lastword $(subst /, ,$(overlay))) \
	$(info "overlay1 = $(overlay) !!!!!!! overlay_name1 = $(overlay_name)")
	srctree.$(overlay_name) := $(overlay) \
	$(info "overlay2 = $(overlay) !!!!!!! overlay_name2 = $(overlay_name)")
	export srctree.$(overlay_name)
endef

$(foreach overlay,$(KERNEL_OVERLAYS),$(eval $(value set_srctree_overlay)))
$(info "AAAA1 srctree.overlay_name = $(srctree.$(overlay_name))")
$(info "AAAA2 srctree.overlay_name = $(srctree)")

# print-variables:
#     @$(foreach v, $(.VARIABLES), $(info $(v) = $($(v))))

# List all variables
all_variables := $(.VARIABLES)

# Filter variables starting with "srctree"
srctree_variables := $(filter src%,$(all_variables))

# Print all srctree variables
print_srctree_variables:
    $(foreach var,$(srctree_variables),$(info $(var): $($(var))))

