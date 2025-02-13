# Aymurzaev-Diyarbek-230277
def typeBasedTransformer(baza):
    transformed = {}
    
  for tipf, value in baza.items():
        if isinstance(value, (int, float)):
            transformed[tipf] = value ** 2
        elif isinstance(value, str):
            transformed[tipf] = value[::-1]
        elif isinstance(value, bool):
            transformed[tipf] = not value
        elif isinstance(value, (list, tuple)):
            transformed[tipf] = type(value)(reversed(value))
        elif isinstance(value, dict):
            if len(set(value.values())) == len(value.values()):
                transformed[tipf] = {v: k for k, v in value.items()}
            else:
                transformed[tipf] = value
        else:
            transformed[tipf] = value
return transformed

