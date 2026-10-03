import math


def check_failure_mode(N_S, N_th, thickness, yield_strength):
    # 1. Convert membrane resultants to stress
    sigma_s = N_S / thickness
    sigma_th = N_th / thickness

    # 2. Calculate von Mises stress from the diagram formula
    sigma_v = math.sqrt(sigma_th**2 - (sigma_th * sigma_s) + sigma_s**2)

    # 3. Output the failure mode
    if sigma_v >= yield_strength:
        failure_mode = "FAILED (Yielded)"
    else:
        failure_mode = "SAFE (No Failure)"

    return sigma_v, failure_mode


# --- Interactive Terminal Input ---
if __name__ == "__main__":
    print("=== O'Neill Cylinder Stress Test ===")

    N_S = float(input("Enter N_S (meridional force): "))
    N_th = float(input("Enter N_th (hoop force): "))
    thickness = float(input("Enter shell thickness: "))
    yield_strength = float(input("Enter material yield strength: "))

    stress, status = check_failure_mode(N_S, N_th, thickness, yield_strength)

    print("\n--- Results ---")
    print(f"Von Mises Stress: {stress:.2f}")
    print(f"Failure Status: {status}")
