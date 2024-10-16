# Application-of-Python-in-the-field-of-Foundation-Engineering
ASSIGNMENT NO. 07

Q.1) # To Determine the bearing capacity of soil with water table

# Input values
bulk_density = float(input("Enter the value of bulk density of soil (kN/m^3): "))
sat_density = float(input("Enter the value of saturated density of soil (kN/m^3): "))
water_density = float(input("Enter the unit weight of water (kN/m^3): "))
df = float(input("Enter the value of depth of footing (m): "))
dw = float(input("Enter the value of water table above footing level (m): "))
dw1 = float(input("Enter the value of water table below the level of footing (m): "))
b = float(input("Enter the value of width of footing (m): "))
nq = float(input("Enter the value of Nq: "))
n = float(input("Enter the value of N (N gamma): "))

# Calculate the submerged density
sub_density = sat_density - water_density
print("Submerged weight of soil is:", sub_density)

# The bearing capacity of soil when the water table is at ground
print("CASE A")
qu_case_a = (sub_density * df * nq) + (0.5 * b * sub_density * n)
print("The value of ultimate bearing capacity of soil is:", qu_case_a)

# Approximate calculation of bearing capacity of soil
rw = 0.5 + 0.5 * (dw / b)
print("The value of Rw is:", rw)
rw1 = 0.5 + 0.5 * (dw1 / b)
print("The value of Rw1 is:", rw1)
qu_case_a_approx = (bulk_density * df * nq * rw) + (0.5 * b * bulk_density * n * rw1)
print("The approximate value of ultimate bearing capacity of soil is:", qu_case_a_approx)

# Case B
print("CASE B")
qu_case_b = (bulk_density * df * nq) + (0.5 * b * sub_density)
print("The value of ultimate bearing capacity is:", qu_case_b)

# Approximate bearing capacity
print("The approximate value of ultimate bearing capacity is:")
rw_case_b = 0.5 + 0.5 * (dw / b)
print("The value of Rw is:", rw_case_b)
rw1_case_b = 0.5 + 0.5 * (dw1 / b)
print("The value of Rw1 is:", rw1_case_b)
qu_case_b_approx = (bulk_density * df * nq * rw_case_b) + (0.5 * b * bulk_density * n * rw1_case_b)
print("The approximate value of ultimate bearing capacity is:", qu_case_b_approx)

# Case C
print("CASE C")
x = float(input("Enter the value of depth of water below footing (m): "))
qu_case_c = (bulk_density * nq) + (0.5 * b * ((bulk_density * x) + (sub_density * (b - x))) * n)
print("The appropriate value of ultimate bearing capacity is:", qu_case_c)

# Re-calculate Rw and Rw1 for Case C
rw_case_c = 0.5 + 0.5 * (dw / b)
print("The value of Rw is:", rw_case_c)
rw1_case_c = 0.5 + 0.5 * (dw1 / b)
print("The value of Rw1 is:", rw1_case_c)
qu_case_c_final = (bulk_density * df * nq * rw_case_c) + (0.5 * b * bulk_density * n * rw1_case_c)
print("The value of ultimate bearing capacity is:", qu_case_c_final)

OUTPUT:
Enter the value of bulk density of soil (kN/m^3): 18
Enter the value of saturated density of soil (kN/m^3): 20
Enter the unit weight of water (kN/m^3): 10
Enter the value of depth of footing (m): 2
Enter the value of water table above footing level (m): 0
Enter the value of water table below the level of footing (m): 0
Enter the value of width of footing (m): 3
Enter the value of Nq: 33
Enter the value of N (N gamma): 34
Submerged weight of soil is: 10.0
CASE A
The value of ultimate bearing capacity of soil is: 1170.0
The value of Rw is: 0.5
The value of Rw1 is: 0.5
The approximate value of ultimate bearing capacity of soil is: 1053.0
CASE B
The value of ultimate bearing capacity is: 1203.0
The approximate value of ultimate bearing capacity is:
The value of Rw is: 0.5
The value of Rw1 is: 0.5
The approximate value of ultimate bearing capacity is: 1053.0
CASE C
Enter the value of depth of water below footing (m): 1
The appropriate value of ultimate bearing capacity is: 2532.0
The value of Rw is: 0.5
The value of Rw1 is: 0.5
The value of ultimate bearing capacity is: 1053.0



Q.2) # To find the ultimate load carrying capacity of pile

# Input values
UCS = float(input("Enter the value of UCS of soil (kN/m^2): "))
Cu = UCS / 2  # Cohesive strength of soil
B = float(input("Enter the value of dimensions of piles (m): "))
L = float(input("Enter the length of pile (m): "))  # Corrected variable name from '1' to 'L'
Alpha = float(input("Enter the value of adhesion factor: "))
Nc = float(input("The value of Nc: "))

# Calculating areas
Ab = B * B  # Base area of the pile
print("The base area of pile is:", Ab, "m^2")

As = 4 * B * L  # Surface area of the pile
print("The value of cohesion of soil is:", Cu, "kN/m^2")

# Ultimate load carrying capacity calculations
Qpu = Cu * Nc * Ab
print("Qpu (Base capacity):", Qpu, "kN")

Qf = Alpha * Cu * As
print("Qf (Friction capacity):", Qf, "kN")

# Total ultimate load carrying capacity
Qu = Qpu + Qf
print("The value of load carrying capacity of pile is (Qu):", Qu, "kN")

OUTPUT:

Enter the value of UCS of soil (kN/m^2): 75
Enter the value of dimensions of piles (m): 0.45
Enter the length of pile (m): 15
Enter the value of adhesion factor: 0.8
The value of Nc: 9
The base area of pile is: 0.2025 m^2
The value of cohesion of soil is: 37.5 kN/m^2
Qpu (Base capacity): 68.34375 kN
Qf (Friction capacity): 810.0 kN
The value of load carrying capacity of pile is (Qu): 878.34375 Kn

Q.3) # To Determine the bearing capacity of soil with water table
BulkDensity = float(input("Enter the value of Bulk Density of soil (kN/m^3): "))
SatDensity = float(input("Enter the value of Saturated Density of soil (kN/m^3): "))
WaterDensity = float(input("Enter the unit weight of water (kN/m^3): "))
Df = float(input("Enter the value of depth of footing (m): "))
B = float(input("Enter the value of width of footing (m): "))
Nq = float(input("Enter the value of Nq: "))
N_Gamma = float(input("Enter the value of N Gamma (N): "))

# Calculate Submerged Density
SubDensity = SatDensity - WaterDensity
print("Submerged weight of soil is:", SubDensity, "kN/m^3")

# Input water table depths above footing
M = int(input("Enter the number of data values for water table above footing level (Dw): "))
Dw = []
for i in range(1, M + 1):
    Depth_Dw = float(input(f"Enter the value of water table above footing level (Dw) for data {i}: "))
    Dw.append(Depth_Dw)

# Calculate Rw for each Dw
Rw_values = []
for depth in Dw:
    Rw = 0.5 + 0.5 * (depth / B)
    Rw_values.append(Rw)
    print(f"The value of Rw for Dw={depth} is:", Rw)

# Input water table depths below footing
N = int(input("Enter the number of data values for water table below footing level (Dw1): "))
Dw1 = []
for j in range(1, N + 1):
    Depth_Dw1 = float(input(f"Enter the value of water table below footing level (Dw1) for data {j}: "))
    Dw1.append(Depth_Dw1)

# Calculate Rw1 for each Dw1
Rw1_values = []
for depth in Dw1:
    Rw1 = 0.5 + 0.5 * (depth / B)
    Rw1_values.append(Rw1)
    print(f"The value of Rw1 for Dw1={depth} is:", Rw1)

# Calculate ultimate bearing capacity (Qu)
# Use the last values of Rw and Rw1 for Qu calculation
Rw_last = Rw_values[-1] if Rw_values else 0
Rw1_last = Rw1_values[-1] if Rw1_values else 0

Qu = (BulkDensity * Df * Nq * Rw_last) + (0.5 * 0.8 * B * BulkDensity * N_Gamma * Rw1_last)
print("Ultimate Bearing Capacity (Qu):", Qu, "kN/m^2")

OUTPUT:
Enter the value of Bulk Density of soil (kN/m^3): 18
Enter the value of Saturated Density of soil (kN/m^3): 20
Enter the unit weight of water (kN/m^3): 10
Enter the value of depth of footing (m): 2
Enter the value of width of footing (m): 3
Enter the value of Nq: 33
Enter the value of N Gamma (N): 34
Submerged weight of soil is: 10.0 kN/m^3
Enter the number of data values for water table above footing level (Dw): 0
Enter the number of data values for water table below footing level (Dw1): 0
Ultimate Bearing Capacity (Qu): 0.0 kN/m^2
