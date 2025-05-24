# impkinpy
Library for mechanics and sidereal time.

# ImpKinPy is library for mechanics and astronomy time

# How to install:
# pip install impkinpy

''' Structure of library:
 folder ImpKinPy >> mechanics          and           astro_time
                        |                                 |
                        |                                 |
            classes Impulse_Energy, Gravity          class Time
'''

# Examples of calling the functions and modules

from ImpKinPy import mechanics as mcn
from ImpKinPy import astro_time as ast

e = mcn.Impulse_Energy()
g = mcn.Gravity("Earth")
t = ast.Time()

e.impulse_k_energy([0.2, 0.5], [[3, 2, 0], [3, 2, 0]])
e.all_impulse_k_energy([[0.6000000000000001, 0.4, 0.0], [1.5, 1.0, 0.0]], [(1.2999999999999998), (3.2499999999999996)])
e.mass_center([5, 2], [[0, 4, 10], [3, 5, 2]], [[2, 5, 8], [2, 5, 7]])
e.rotate_coords_2D([2, 5], 45)
e.rotate_coords_3D([2, 5, 7], 45, "XY")
e.rotate_coords_nD([2, 5, 7, 20, 13], 45, ["x4", "x1"]) 

g.trajectory_2_parameters(v0=10, angle=100)
g.pendulum("rod", "end", 100, 10, 45, 20, 5, 0, 0, 0, 0)
g.nD_pendulum("symplex", 5, 5, [["x1", "x2"], ["x3", "x2"]], [50, 20], [0, 0], 100, 1000)
g.plot_nD_pendulum('self.nD_pendulum("hypersphere", 5, 5, [["x1", "x2"], ["x3", "x2"]], [50, 20], [0, np.pi/2], 100, 1000)')
g.plot_trajectory("self.trajectory_2_parameters(Height=10, v0x=20)")
g.plot_pendulum('self.pendulum("rod", "end", 100, 10, 45, 20, 5, 0, 0, 0, 0)')

t.JD(2025, 5, 24, 14, 28, 0)
t.day_number(5, 31, False)
t.GST_date_Earth(2025, 5, 24, 14, 28, 0)
t.LST_date_Earth(15, 2025, 5, 24, 14, 28, 0)
t.PTC_date(86400, 0, True, 2025, 5, 24, 14, 28, 0)
t.PTC_offset(True, 0, 2451540.0, 24.65)
t.PTC_ST_date(86400, 44795.9998, True, 12.0, 2025, 5, 24, 14, 28, 0)
