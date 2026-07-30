#  Wallpapers
## Nix package

1. **Use [nix flakes](https://wiki.nixos.org/wiki/Flakes)**:

2. Add the following to your `flake.nix` file:
   
```nix
inputs = {
  wallpapers.url = "github:abdellah-azarfane/wallpapers";
  # ...
};
```

3. Then, in your Home Manager configuration:

```nix
{
  inputs,
  pkgs,
  ...
}: {
  home.file = {
    "path/to/dir" = {
      source = inputs.gruvbox-wallpapers.packages."${pkgs.stdenv.hostPlatform.system}".default;
      recursive = true;
    };
  };
}
```

## Disclaimer 

Most of the images shared here are community contributions, and their original sources are often unknown. If you are the rightful owner of any image and would like it removed, please contact me by opening an issue. For any use beyond personal scope, I recommend performing a reverse image search to verify the origin.
