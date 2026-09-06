# Proyecto_SQL
Proyecto de curso


VERIFICACIÓN DE DATOS NULOS
```sql
-- TABLA customers
SELECT COUNT(*)
FROM customers
WHERE customer_id IS NULL
   OR customer_name IS NULL
   OR customer_type IS NULL
   OR credit_terms_days IS NULL
   OR primary_freight_type IS NULL
   OR account_status IS NULL
   OR contract_start_date IS NULL
   OR annual_revenue_potential IS NULL;

-- TABLA drivers
SELECT COUNT(*)
FROM drivers
WHERE driver_id IS NULL
   OR first_name IS NULL
   OR last_name IS NULL
   OR hire_date IS NULL
   OR termination_date IS NULL
   OR license_number IS NULL
   OR license_state IS NULL
   OR date_of_birth IS NULL
   OR home_terminal IS NULL
   OR employment_status IS NULL
   OR cdl_class IS NULL
   OR years_experience IS NULL;

-- TABLA trucks
SELECT COUNT(*)
FROM trucks
WHERE truck_id IS NULL
   OR unit_number IS NULL
   OR make IS NULL
   OR model_year IS NULL
   OR vin IS NULL
   OR acquisition_date IS NULL
   OR acquisition_mileage IS NULL
   OR fuel_type IS NULL
   OR tank_capacity_gallons IS NULL
   OR status IS NULL
   OR home_terminal IS NULL;

-- TABLA routes
SELECT COUNT(*)
FROM routes
WHERE route_id IS NULL
   OR origin_city IS NULL
   OR origin_state IS NULL
   OR destination_city IS NULL
   OR destination_state IS NULL
   OR typical_distance_miles IS NULL
   OR base_rate_per_mile IS NULL
   OR fuel_surcharge_rate IS NULL
   OR typical_transit_days IS NULL;

-- TABLA trips
SELECT COUNT(*)
FROM trips
WHERE trip_id IS NULL
   OR load_id IS NULL
   OR driver_id IS NULL
   OR truck_id IS NULL
   OR trailer_id IS NULL
   OR dispatch_date IS NULL
   OR actual_distance_miles IS NULL
   OR actual_duration_hours IS NULL
   OR fuel_gallons_used IS NULL
   OR average_mpg IS NULL
   OR idle_time_hours IS NULL
   OR trip_status IS NULL;

-- TABLA fuel_purchases
SELECT COUNT(*)
FROM fuel_purchases
WHERE fuel_purchase_id IS NULL
   OR trip_id IS NULL
   OR truck_id IS NULL
   OR driver_id IS NULL
   OR purchase_date IS NULL
   OR location_city IS NULL
   OR location_state IS NULL
   OR gallons IS NULL
   OR price_per_gallon IS NULL
   OR total_cost IS NULL
   OR fuel_card_number IS NULL;
```
Se encontraron los siguientes datos nulos:



VERIFICACIÓN DE DUPLICADOS
```sql
-- TABLA customers
SELECT customer_id, COUNT(*)
FROM customers
GROUP BY customer_id
HAVING COUNT(*) > 1;

-- TABLA drivers
SELECT driver_id, COUNT(*)
FROM drivers
GROUP BY driver_id
HAVING COUNT(*) > 1;

-- TABLA trucks
SELECT truck_id, COUNT(*)
FROM trucks
GROUP BY truck_id
HAVING COUNT(*) > 1;

-- TABLA routes
SELECT route_id, COUNT(*)
FROM routes
GROUP BY route_id
HAVING COUNT(*) > 1;

-- TABLA trips
SELECT trip_id, COUNT(*)
FROM trips
GROUP BY trip_id
HAVING COUNT(*) > 1;

-- TABLA fuel_purchases
SELECT fuel_purchase_id, COUNT(*)
FROM fuel_purchases
GROUP BY fuel_purchase_id
HAVING COUNT(*) > 1
```
No se encontraron valores duplicados en las tablas a trabajar