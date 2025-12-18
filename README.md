# uber_driver.sql
Mysql project 

CREATE TABLE drivers (
    driver_id INT PRIMARY KEY IDENTITY(1,1),
    driver_name VARCHAR(100) NOT NULL,
    vehicle_type VARCHAR(10) NOT NULL,
    vehicle_name VARCHAR(50) NOT NULL,
    city VARCHAR(50) NOT NULL,
    status VARCHAR(15) NOT NULL,
    issue VARCHAR(MAX),
    trip_taken INT
    created_at DATETIME2 DEFAULT GETDATE(),
    updated_at DATETIME2 DEFAULT GETDATE()
);
GO

-- Insert 55+ Driver Records with diverse vehicle types
INSERT INTO drivers (driver_name, vehicle_type, vehicle_name, city, status, issue, trip_taken) VALUES
-- Bike drivers
('Rajesh Kumar', 'bike', 'Honda Activa', 'Bangalore', 'active', 'None', 245),
('Priya Sharma', 'bike', 'TVS Jupiter', 'Mumbai', 'active', 'Low earning concern', 189),
('Amit Patel', 'bike', 'Suzuki Access', 'Delhi', 'waitlisted', 'Asking extra money from customers', 45),
('Sunita Reddy', 'bike', 'Hero Maestro', 'Hyderabad', 'rejected', 'Duplicate ID found', 12),
('Vijay Singh', 'bike', 'Yamaha Fascino', 'Pune', 'applied', 'Under verification', 0),
('Mohammed Ali', 'bike', 'Honda Dio', 'Bangalore', 'active', 'Vehicle maintenance issue', 312),
('Kavita Nair', 'bike', 'TVS Ntorq', 'Kochi', 'active', 'Health issue - diabetes management', 156),
('Sneha Desai', 'bike', 'Suzuki Burgman', 'Ahmedabad', 'active', 'Personal issue - family emergency', 203),
('Anjali Verma', 'bike', 'Honda Activa 6G', 'Jaipur', 'applied', 'Documents under review', 0),
('Pooja Singh', 'bike', 'TVS Jupiter ZX', 'Delhi', 'active', 'None', 278),
('Pallavi Jain', 'bike', 'Hero Pleasure', 'Jaipur', 'active', 'Seasonal issue - tourist season', 167),
('Seema Roy', 'bike', 'Yamaha Ray ZR', 'Guwahati', 'reactivation', 'Document issue - bank details update', 89),

-- Auto drivers
('Lakshmi Iyer', 'auto', 'Bajaj RE Auto', 'Chennai', 'reactivation', 'Document issue - expired license', 134),
('Deepak Mehta', 'auto', 'Piaggio Ape', 'Mumbai', 'waitlisted', 'Operating multiple vehicles with different IDs', 67),
('Rahul Gupta', 'auto', 'Mahindra Alfa', 'Delhi', 'rejected', 'Duplicate ID - account suspended', 23),
('Karthik Rao', 'auto', 'TVS King', 'Bangalore', 'active', 'Seasonal issue - monsoon affecting rides', 289),
('Suresh Babu', 'auto', 'Bajaj Maxima', 'Chennai', 'reactivation', 'Document issue - insurance expired', 145),
('Arun Kumar', 'auto', 'Piaggio Ape City', 'Bangalore', 'waitlisted', 'Customer complaints - overcharging', 56),
('Ramesh Pillai', 'auto', 'Mahindra Treo', 'Kochi', 'rejected', 'Duplicate ID verification failed', 18),
('Sandeep Joshi', 'auto', 'Bajaj RE Compact', 'Pune', 'reactivation', 'Document issue - RC renewal pending', 112),
('Vikram Malhotra', 'auto', 'TVS King Deluxe', 'Chandigarh', 'applied', 'Background verification in progress', 0),
('Rekha Patel', 'auto', 'Piaggio Ape Auto', 'Ahmedabad', 'waitlisted', 'Multiple vehicle operation suspected', 72),
('Govind Sharma', 'auto', 'Mahindra Alfa Plus', 'Indore', 'active', 'Seasonal issue - wedding season high demand', 234),
('Manoj Tiwari', 'auto', 'Bajaj RE 4S', 'Varanasi', 'rejected', 'Duplicate ID - multiple accounts', 34),
('Harish Bhat', 'auto', 'TVS King Duramax', 'Mangalore', 'reactivation', 'Document issue - PAN card update needed', 98),
('Swati Kulkarni', 'auto', 'Piaggio Ape Xtra', 'Pune', 'waitlisted', 'Asking extra fare from passengers', 61),
('Nandini Rao', 'auto', 'Mahindra Treo Zor', 'Mysore', 'applied', 'Documents submitted', 0),
('Geeta Menon', 'auto', 'Bajaj RE Electric', 'Trivandrum', 'reactivation', 'Document issue - address proof pending', 87),
('Sanjay Mishra', 'auto', 'TVS King Electric', 'Bhopal', 'rejected', 'Duplicate ID found in system', 29),
('Naresh Yadav', 'auto', 'Piaggio Ape E-City', 'Delhi', 'waitlisted', 'Driving multiple vehicles with different IDs', 54),
('Usha Rani', 'auto', 'Mahindra Alfa Load', 'Ranchi', 'rejected', 'Duplicate ID verification failed', 15),
('Bharti Agarwal', 'auto', 'Bajaj Qute', 'Surat', 'waitlisted', 'Customer complaints about extra charges', 48),

-- Car drivers
('Neha Kapoor', 'car', 'Hyundai Creta', 'Mumbai', 'active', 'Low earning - night shift preference', 456),
('Divya Krishnan', 'car', 'Hyundai Venue', 'Hyderabad', 'active', 'Vehicle issue - AC malfunction', 389),
('Meera Devi', 'car', 'Toyota Etios', 'Lucknow', 'active', 'Health issue - back pain', 267),
('Shalini Reddy', 'car', 'Honda City', 'Hyderabad', 'active', 'Low earning complaint', 412),
('Anita Deshmukh', 'car', 'Toyota Innova', 'Nagpur', 'active', 'Personal issue - child care', 334),
('Pradeep Nair', 'car', 'Maruti Ertiga', 'Kochi', 'active', 'Vehicle issue - tire replacement needed', 298),
('Ravi Chandra', 'car', 'Hyundai Venue', 'Visakhapatnam', 'active', 'None', 367),
('Ashok Kumar', 'car', 'Toyota Etios', 'Coimbatore', 'active', 'Health issue - routine checkup', 289),
('Kavita Bose', 'car', 'Maruti Ertiga', 'Kolkata', 'active', 'Low earning due to area preference', 245),
('Prakash Shetty', 'car', 'Toyota Innova', 'Bangalore', 'active', 'Vehicle issue - engine servicing', 501),
('Madhuri Sinha', 'car', 'Hyundai Creta', 'Patna', 'applied', 'Application under review', 0),
('Dinesh Pillai', 'car', 'Honda City', 'Chennai', 'reactivation', 'Document issue - fitness certificate expired', 178),
('Radha Krishna', 'car', 'Maruti Dzire', 'Hyderabad', 'active', 'Personal issue - relocation planning', 423),
('Ajay Thakur', 'car', 'Hyundai Venue', 'Shimla', 'active', 'Seasonal issue - winter tourism', 198),
('Mohan Das', 'car', 'Toyota Etios', 'Bhubaneswar', 'active', 'None', 312),
('Kishore Kumar', 'car', 'Maruti Ertiga', 'Vijayawada', 'active', 'Health issue - eye checkup scheduled', 356),
('Brijesh Pandey', 'car', 'Honda Amaze', 'Kanpur', 'active', 'Low earning - switching to peak hours', 234),
('Archana Iyer', 'car', 'Maruti Dzire', 'Kochi', 'applied', 'Waiting for onboarding', 0),
('Nitesh Agarwal', 'car', 'Toyota Innova', 'Mumbai', 'active', 'Vehicle issue - brake system check', 489),
('Shilpa Hegde', 'car', 'Hyundai Creta', 'Bangalore', 'waitlisted', 'Multiple account operation suspected', 78),
('Ranjit Singh', 'car', 'Honda City', 'Amritsar', 'active', 'Seasonal issue - festival rush', 401),
('Vaishali Chopra', 'car', 'Maruti Swift', 'Delhi', 'rejected', 'Duplicate ID - policy violation', 41),
('Ganesh Murthy', 'car', 'Hyundai Venue', 'Chennai', 'active', 'Personal issue - health insurance claim', 378),
('Sunil Kapoor', 'car', 'Maruti Swift', 'Bangalore', 'active', 'None', 445),
('Preeti Agarwal', 'car', 'Honda Jazz', 'Mumbai', 'active', 'Low earning - peak hour strategy', 412),
('Anil Verma', 'car', 'Hyundai i20', 'Delhi', 'active', 'Vehicle issue - suspension check needed', 367);
GO


--SELECT, COUNT(*) as driver_count
--FROM drivers
--GROUP BY status
--ORDER BY driver_count DESC;

SELECT
    driver_name,
    city,
    vehicle_name,
    issue,
    status
FROM drivers
WHERE status = 'active';

SELECT vehicle_type, COUNT(*) as active_count
FROM drivers
WHERE status = 'active'
GROUP BY vehicle_type;


SELECT status AS dp_status, COUNT(*) AS driver_count
FROM drivers
GROUP BY status;

SELECT*
FROM drivers
where  city in ('Chennai') ;

SELECT DVP.city, DVP.vehicle_name
FROM drivers AS DVP
WHERE DVP.vehicle_name LIKE '%Bajaj%';

SELECT 
    city,SUM(trip_taken) AS total_trips_by_city
FROM drivers
GROUP BY city
ORDER BY total_trips_by_city DESC;
